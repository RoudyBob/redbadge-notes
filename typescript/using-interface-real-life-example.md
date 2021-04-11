# Using Interface - Real Life Example

* Using the Chuck Norris joke API
* First create the interface based on what you plan on getting back from the API
* Then you can take the json response and run it through the interface
* Don't forget to tsc &lt;filename&gt; after you make changes to the Typescript source!

{% tabs %}
{% tab title="XML/HTML/SVG" %}
```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <div>
        <img id="jokeIcon"></img>
        <p id="jokeText"></p>
        <p id="jokeId"></p>
        <a id="jokeUrl"href="https://api.chucknorris.io/jokes/ybW0PJGRQymx_2In2TvtzA">Link To Joke</a>
    </div>
    <script src="./fetch-ts.js"></script>
</body>
</html>
```
{% endtab %}

{% tab title="" %}
```typescript
const jokeIcon = document.getElementById("jokeIcon") as HTMLImageElement;
const jokeText = document.getElementById("jokeText") as HTMLParagraphElement;
const jokeId = document.getElementById("jokeId") as HTMLParagraphElement;
const jokeUrl = document.getElementById("jokeUrl") as HTMLLinkElement;

interface IChuckResponse {
    icon_url: string,
    id: string,
    url?: string,
    value: string
}

function fetchJoke() {
    let url: string = "https://api.chucknorris.io/jokes/random";
    fetch(url)
    .then((res) => res.json())
    .then((data:IChuckResponse) => {
        jokeIcon.src = data.icon_url;
        jokeText.innerHTML = data.value;
        jokeId.innerHTML = data.id;
        jokeUrl.href = data.url;
    })
};

fetchJoke();
```
{% endtab %}
{% endtabs %}

