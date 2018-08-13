# BlazorSEO
Invoke JavaScript functions from .NET in blazor apps using JavaScript interop

## Steps
* Add the code in your razor page<br>
`protected override async Task OnInitAsync()`<br>
`{`<br>
 `   await JSRuntime.Current.InvokeAsync<string> ("betterSeo.metaChanger","Your title","Your Description","Your keywords");`<br>
`}`<br>
* That will call the javascript function<br>
`window.betterSeo = {`<br>
`  metaChanger: function(title, description, keywords) {`<br>
   `   document.title = title;`<br>
   `   document.getElementsByTagName("meta")["description"].content = description;`<br>
   `   document.getElementsByTagName("meta")["keywords"].content = keywords;`<br>
   `   return console.log("Seo by amine smahi");`<br>
  `}`<br>
`};`<br>
* And this is it, Now the meta tags will be updated on the client request

## Screenshot
![SEO blazor serverside ](https://user-images.githubusercontent.com/24621701/43996330-a280112c-9db8-11e8-9731-a0ce5890e9bb.png)
