# BlazorSEO
Invoke JavaScript functions from .NET in blazor apps using JavaScript interop

## Steps
* Add the code in your razor page
`protected override async Task OnInitAsync()`
`{`
 `   await JSRuntime.Current.InvokeAsync<string> ("betterSeo.metaChanger","Your title","Your Description","Your keywords");`
`}`
* That will code the javascript function
`window.betterSeo = {`
`  metaChanger: function(title, description, keywords) {`
   ` document.title = title;`
   ` document.getElementsByTagName("meta")["description"].content = description;`
   ` document.getElementsByTagName("meta")["keywords"].content = keywords;`
   ` return console.log("Seo by amine smahi");`
  `}`
`};`
* And this is it, Now the meta tags will be updated on the client request
