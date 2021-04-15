# Many to Many

A Many to many relationship is one where many things can be related to many others within a database.

This is done with a join table that can but is not required to have additional columns. consider the following example.

    CREATE TABLE `Artist` (
    `id` INT PK,
    `first_name` varchar(255) NOT NULL,
    `last_name` varchar(255) NOT NULL,
    PRIMARY KEY (`id`)
    );

    CREATE TABLE `album` (
    `id` INT PK,
    `title` varchar(255) DEFAULT NULL,
    PRIMARY KEY (`id`)
    );

    CREATE TABLE `Artist_album` (
    `Artist_id` INT NOT NULL,
    `album_id` INT NOT NULL,
    `role` varchar(255), <--optional field to show the roll of the artist within the album i.e. drummer.
    PRIMARY KEY (`Artist_id`,`album_id`),
    CONSTRAINT `Artist_id_fk` FOREIGN KEY (`Artist_id`) REFERENCES `Artist` (`id`),
    CONSTRAINT `album_id_fk` FOREIGN KEY (`album_id`) REFERENCES `album` (`id`)
    );