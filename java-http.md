HttpUrlConnection 
https://docs.oracle.com/javase/8/docs/api/java/net/HttpURLConnection.html

HttpUrlConnection is used to make a single  HTTP request you can use it do do most things you typically would with an http request such as handle cooks set headers etc.

A sample call would look like this:

From https://www.baeldung.com/java-http-request

    public class FullResponseBuilder {
        public static String getFullResponse(HttpURLConnection con) throws IOException {
            StringBuilder fullResponseBuilder = new StringBuilder();

            // read status and message
            fullResponseBuilder.append(con.getResponseCode())
            .append(" ")
            .append(con.getResponseMessage())
            .append("\n");
            // read headers
            con.getHeaderFields().entrySet().stream()
            .filter(entry -> entry.getKey() != null)
            .forEach(entry -> {
                fullResponseBuilder.append(entry.getKey()).append(": ");
                List headerValues = entry.getValue();
                Iterator it = headerValues.iterator();
                if (it.hasNext()) {
                    fullResponseBuilder.append(it.next());
                    while (it.hasNext()) {
                        fullResponseBuilder.append(", ").append(it.next());
                    }
                }
                fullResponseBuilder.append("\n");
            });
            // read response content
            if (status > 299) {
                streamReader = new InputStreamReader(con.getErrorStream());
            } else {
                streamReader = new InputStreamReader(con.getInputStream());
            }

            return fullResponseBuilder.toString();
        }
    }