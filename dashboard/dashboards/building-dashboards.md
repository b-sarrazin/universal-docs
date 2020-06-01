# Building Dashboards

When building dashboards, you will pick one of the two built in dashboard frameworks. The components that are available for that framework will different. You can find examples of each of the frameworks at the below links. 

* [Universal Dashboard v2](https://github.com/ironmansoftware/universal-dashboard/tree/master/src/v2/example)
* [Universal Dashboard v3](https://github.com/ironmansoftware/universal-dashboard/tree/master/src/v3/example)

{% hint style="info" %}
All the documentation on this page will be referencing the v3 framework. 
{% endhint %}

Dashboards can contain one or more pages. The simplest dashboard will contain a single page with some content. You can call any PowerShell cmdlet that is available on your machine to populate your dashboard. 

Here's an example of simple dashboard that displays some text. 

```text
New-UDDashboard -Title 'My New Dashboard' -Content {
    New-UDTypography -Text 'Hello!'
}
```

### Pages

You can specify multiple pages within a dashboard. Each page defines a route. As for v3, all pages are dynamic. PowerShell will execute on each page load to render the new page. Since UD is a single page application, the web browser does not need to refresh the entire web page when navigating between the different dashboard pages. 

```text
$Pages += New-UDPage -Name 'My Home Page' -Content {}
$Pages += New-UDPage -Name 'Diagnostics' -Content {}
New-UDDashboard -Pages $Pages -Title 'Dashboard'
```
