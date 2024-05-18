# Text ocr api C# calling source code

```c#
var client = new HttpClient();
var request = new HttpRequestMessage(HttpMethod.Post, "https://netocr.com/api/recogliu.do");
var content = new MultipartFormDataContent();
content.Add(new StringContent("/9j"), "img");
content.Add(new StringContent("M***********g"), "key");
content.Add(new StringContent("3***********6"), "secret");
content.Add(new StringContent("1993"), "typeId");
content.Add(new StringContent("json"), "format");
request.Content = content;
var response = await client.SendAsync(request);
response.EnsureSuccessStatusCode();
Console.WriteLine(await response.Content.ReadAsStringAsync()); 
```