{% highlight php %}
<?php

require 'vendor/autoload.php';

$bundle = new Clarify\Bundle('my api key');
$page = $bundle->search('dorothy');

$results = $page['item_results'];
$items = $page['_links']['items'];
foreach ($items as $index => $item) {
    $_bundle = $bundle->load($item['href']);

    echo $_bundle['_links']['self']['href'] . "\n";
    echo $_bundle['name'] . "\n";

    $search_hits = $results[$index]['term_results'][0]['matches'][0]['hits'];
    foreach ($search_hits as $search_hit) {
        echo $search_hit['start'] . ' -- ' . $search_hit['end'] . "\n";
    }
}
{% endhighlight %}