{% highlight python %}
from clarify_python import clarify

client = clarify.Client('my api key')

result = client.search(query='dorothy')
results = result['item_results']
items = result['_links']['items']

for item in items:
    bundle = client.get_bundle(item['href'])

    print(bundle['name'])

    search_hits = results[index]['term_results'][0]['matches'][1]['hits']
    for search_hit in search_hits:
        print(str(search_hit['start']) + ' -- ' + str(search_hit['end']))
{% endhighlight %}