# GraphQL

@Connection annotation within GraphQl is how you define the one-to-one, one-to-many, and many-to-one relationships within models.

    @connection(keyName: String, fields: [String!]) on FIELD_DEFINITION

one-to-one is defined by placing a @Connection within one model.

    type m1 @model {
    id: ID!
    name: String
    m1: M1 @connection
    }

    type m2 @model {
    id: ID!
    name: String!
    }

one-to-many is done similarly but by also including a key reference and adding that key to the target model

    type M1 @model {
    id: ID!
    name: String!
    m2: [M2] @connection(keyName: "byM1", fields: ["id"])
    }

    type M2 @model {
    @key(name: "byM1", fields: ["m1ID", "name"]) {
    id: ID!
    name: String!
    }

You can also make M2 aware of M1 in this case by adding a m1 line to the end

    m1: M! @connection(fields: ["m1ID"]

many-to-many connections can be created by using a join table and multiple many-to-one connections. For example the below code form https://docs.amplify.aws/cli/graphql-transformer/connection#belongs-to demonstrates this for users and posts they have modified.

    type Post @model {
    id: ID!
    title: String!
    editors: [PostEditor] @connection(keyName: "byPost", fields: ["id"])
    }

    # Create a join model and disable queries as you don't need them
    # and can query through Post.editors and User.posts
    type PostEditor
    @model(queries: null)
    @key(name: "byPost", fields: ["postID", "editorID"])
    @key(name: "byEditor", fields: ["editorID", "postID"]) {
    id: ID!
    postID: ID!
    editorID: ID!
    post: Post! @connection(fields: ["postID"])
    editor: User! @connection(fields: ["editorID"])
    }

    type User @model {
    id: ID!
    username: String!
    posts: [PostEditor] @connection(keyName: "byEditor", fields: ["id"])
    }

