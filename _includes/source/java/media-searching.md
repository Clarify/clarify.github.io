{% highlight java %}
import io.clarify.api.*;
import java.net.URI;

public class App {
    public static void main(String[] args) throws Exception {
        String appKey = "my api key";

        // Construct the API client
        ClarifyClient client = new ClarifyClient(appKey);

        // Search your media by query string
        String query = "dorothy";
        BundleSearchResults bundleSearchResults = client.searchBundles(query);
        JSONArray itemResults = bundleSearchResults.getItemResults();

        for(int i=0;i&lt;itemResults.length();i++) {
            JSONObject item = (JSONObject)itemResults.get(i);
            System.out.println("score="+item.get("score"));
        }
    }
}
{% endhighlight %}