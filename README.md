## Signin G+ Plugin for Xamarin Forms
Package Nuget for Signin G+ in Xamarin Forms

**Platform Support**

|Platform|Version|
| ------------------- | :-----------: |
|Xamarin.Android|API 14+|

### Android specific in your BaseActivity or MainActivity (for Xamarin.Forms) add this code:
```csharp
protected override void OnActivityResult(int requestCode, Result resultCode, Intent data)
{
    base.OnActivityResult(requestCode, resultCode, data);
    CodeFacil.Forms.GoogleApi_Android.OnActivityResult(requestCode, resultCode, data);
}
```

### API Usage

Call **CrossCodeFacil.Current.GoogleApi().SignIn** from any project or PCL to gain access to APIs.

```csharp
CrossCodeFacil.Current.GoogleApi().SignIn((result) =>
{
    if (result.IsSuccess)
    {
       GoogleApiAccount account = result.Account; 
    }
    else
    {
        GoogleApiStatus status = result.Status;
    }
}
```

### Available Account Info

```csharp
public class GoogleApiAccount
{
    public string DisplayName { get; set; }
    public string Email { get; set; }
    public string FamilyName { get; set; }
    public string GivenName { get; set; }
    public string Id { get; set; }
    public string IdToken { get; set; }
    public GoogleApiPhotoUrl PhotoUrl { get; set; }
}

public class GoogleApiStatus
{
    public int StatusCode { get; set; }
    public string StatusMessage { get; set; }
}

```

Thanks!

# License
Licensed under main repo license(MIT)
