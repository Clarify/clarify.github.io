{% highlight java %}
import io.clarify.api.*;
import java.net.URI;

public class App {
    public static void main(String[] args) throws Exception {
        String appKey = "my api key";

        // Construct the API client
        ClarifyClient client = new ClarifyClient(appKey);

        // Create your first bundle using an example audio file
        String name = "Dorothy and the Wizard of Oz";
        URI mediaUrl =  URI.create("http://media.clarify.io/audio/books/dorothyandthewizardinoz_01_baum_64kb.mp3");
        Bundle bundle = client.createBundle(name, mediaUrl);

        System.out.println(bundle.id());
    }
}
{% endhighlight %}