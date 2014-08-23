coffee
======
using (var client = new HttpClient())
{
  client.BaseAddress = new Uri(ENDPOINT);
//  WebRequest.DefaultWebProxy = new WebProxy("127.0.0.1", 8888) { BypassProxyOnLocal = false };
  const string auth = USERNAME + ":" + APITOKEN;
  byte[] authBytes = Encoding.ASCII.GetBytes(auth);
  client.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue("Basic", Convert.ToBase64String(authBytes));
}
