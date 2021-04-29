# Getting Started for Xamarin.Forms SfAutoComplete

The [Xamarin Autocomplete](https://www.syncfusion.com/xamarin-ui-controls/xamarin-autocomplete?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples) control is highly optimized to quickly load and populate suggestions from a large volume of data depending on the users’ input characters. It provides a simpler way to complete the text based on the characters that the user has entered before. It also provides option to choose a suggestion from drop down or append a suggestion to the text directly.

## <a name="description"></a>Description ##

### Initializing AutoComplete

Import the SfAutoComplete namespace in respective Page as shown below:

###### Xaml
```xaml
xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms" 
```
###### C#
```C#
using Syncfusion.SfAutoComplete.XForms;
```

Then initialize an empty autocomplete as shown below,

###### Xaml
```xaml
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"
             xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:local="clr-namespace:AutocompleteSample"
             x:Class="AutocompleteSample.MainPage">
    <StackLayout 
        VerticalOptions="Start" 
        HorizontalOptions="Start"
        Padding="30">
        <autocomplete:SfAutoComplete x:Name="autoComplete"
                                     HeightRequest="40"/>
    </StackLayout>
</ContentPage>
```
###### C#
```C#
using Syncfusion.SfAutoComplete.XForms;
using System.Collections.Generic;
using Xamarin.Forms;

namespace AutocompleteSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout()
            {
                VerticalOptions = LayoutOptions.Start,
                HorizontalOptions = LayoutOptions.Start,
                Padding = new Thickness(30)
            };

            SfAutoComplete autoComplete = new SfAutoComplete()
            {
                HeightRequest = 40
            };

            stackLayout.Children.Add(autoComplete);
            this.Content = stackLayout;
        }
    }
}
```
### Populating AutoComplete with Data

Now, let us create a simple list of country names and set it as the `AutoCompleteSource` of AutoComplete.

###### Xaml
```xaml
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"
             xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:local="clr-namespace:AutocompleteSample"
             x:Class="AutocompleteSample.MainPage">
    <StackLayout 
        VerticalOptions="Start" 
        HorizontalOptions="Start"
        Padding="30">
        <autocomplete:SfAutoComplete x:Name="autoComplete"
                                     HeightRequest="40">
            <autocomplete:SfAutoComplete.AutoCompleteSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>India</x:String>
                    <x:String>Uganda</x:String>
                    <x:String>Ukraine</x:String>
                    <x:String>Canada</x:String>
                    <x:String>United Arab Emirates</x:String>
                </ListCollection:List>
            </autocomplete:SfAutoComplete.AutoCompleteSource>
        </autocomplete:SfAutoComplete>
    </StackLayout>
</ContentPage> 
```
###### C#
```C#
using Syncfusion.SfAutoComplete.XForms;
using System.Collections.Generic;
using Xamarin.Forms;

namespace AutocompleteSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout()
            {
                VerticalOptions = LayoutOptions.Start,
                HorizontalOptions = LayoutOptions.Start,
                Padding = new Thickness(30)
            };

            SfAutoComplete autoComplete = new SfAutoComplete()
            {
                HeightRequest = 40,
                AutoCompleteSource = new List<string>()
                {
                    "India",
                    "Uganda",
                    "Ukraine", 
                    "Canada",
                    "United Arab Emirates"
                }
            };

            stackLayout.Children.Add(autoComplete);
            this.Content = stackLayout;
        }
    }
}
```
Refer [`this`](https://help.syncfusion.com/xamarin/sfautocomplete/populating-data?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples) link to learn more about the options available in SfAutoComplete to populate data.

### Configuring filter options

By default, items are filtered in “StartsWith” case insensitive mode and the suggestions are displayed in a drop down popup. Autocomplete can now filter suggestions.

Here in this example, let us configure it to “Contains” case sensitive filter mode. This can be achieved by setting `SuggestionMode` property.

###### Xaml
```xaml
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"
             xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:local="clr-namespace:AutocompleteSample"
             x:Class="AutocompleteSample.MainPage">
    <StackLayout 
        VerticalOptions="Start" 
        HorizontalOptions="Start"
        Padding="30">
        <autocomplete:SfAutoComplete x:Name="autoComplete"
                                     HeightRequest="40"
                                     SuggestionMode="ContainsWithCaseSensitive">
            <autocomplete:SfAutoComplete.AutoCompleteSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>India</x:String>
                    <x:String>Uganda</x:String>
                    <x:String>Ukraine</x:String>
                    <x:String>Canada</x:String>
                    <x:String>United Arab Emirates</x:String>
                    <x:String>France</x:String>
                    <x:String>United Kingdom</x:String>
                    <x:String>China</x:String>
                    <x:String>United States</x:String>
                    <x:String>Japan</x:String>
                    <x:String>Angola</x:String>
                </ListCollection:List>
            </autocomplete:SfAutoComplete.AutoCompleteSource>
        </autocomplete:SfAutoComplete>
    </StackLayout>
</ContentPage>
```
###### C#
```C#
using Syncfusion.SfAutoComplete.XForms;
using System.Collections.Generic;
using Xamarin.Forms;

namespace AutocompleteSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout()
            {
                VerticalOptions = LayoutOptions.Start,
                HorizontalOptions = LayoutOptions.Start,
                Padding = new Thickness(30)
            };

            SfAutoComplete autoComplete = new SfAutoComplete()
            {
                HeightRequest = 40,
                SuggestionMode = SuggestionMode.ContainsWithCaseSensitive,
                AutoCompleteSource = new List<string>()
                {
                    "India",
                    "Uganda",
                    "Ukraine", 
                    "Canada",
                    "United Arab Emirates",
                    "France", 
                    "United Kingdom",
                    "China", 
                    "United States",
                    "Japan",
                    "Angola"
                }
            };

            stackLayout.Children.Add(autoComplete);
            this.Content = stackLayout;
        }
    }
}
```
Refer [`this`](https://help.syncfusion.com/xamarin/autocomplete/autocomplete-filtering-options?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples) link to learn more about the options available in SfAutoComplete to filter suggestions.

## Related links
[Learn More about Xamarin Autocomplete](https://www.syncfusion.com/xamarin-ui-controls/xamarin-autocomplete?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples) <br/><br/>
[Download Free Trial](https://www.syncfusion.com/downloads?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples) <br/><br/>
[Pricing](https://www.syncfusion.com/sales/products/xamarin?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples) <br/><br/>
[Documentation](https://help.syncfusion.com/xamarin/autocomplete/getting-started?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples) <br/><br/>
[Online Examples](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/AutoComplete?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples) <br/><br/>
[Community Forums](https://www.syncfusion.com/forums/xamarin.forms/sfautocomplete?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples) <br/><br/>
[Suggest a feature](https://www.syncfusion.com/feedback/xamarin-forms?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples)

## About Syncfusion Xamarin UI Controls
Syncfusion's [Xamarin.Forms](https://www.syncfusion.com/xamarin-ui-controls?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples) library offers over 155 UI controls to create cross-platform native mobile apps for iOS, Android, UWP and macOS platforms from a single C# code base. In addition to Autocomplete, we provide popular Xamarin controls such as [DataGrid](https://www.syncfusion.com/xamarin-ui-controls/xamarin-datagrid?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples), [Charts](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples),
[Scheduler](https://www.syncfusion.com/xamarin-ui-controls/xamarin-scheduler?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples), [Diagram](https://www.syncfusion.com/xamarin-ui-controls/xamarin-diagram?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples), and [Maps](https://www.syncfusion.com/xamarin-ui-controls/xamarin-maps?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples).

## About Syncfusion
Founded in 2001 and headquartered in Research Triangle Park, N.C., Syncfusion has more than 23,000+ customers and more than 1 million users, including large financial institutions, Fortune 500 companies, and global IT consultancies.
 
Today, we provide 1600+ controls and frameworks for web
([Blazor](https://www.syncfusion.com/blazor-components?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples),
[ASP.NET Core](https://www.syncfusion.com/aspnet-core-ui-controls?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples),
[ASP.NET MVC](https://www.syncfusion.com/aspnet-mvc-ui-controls?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples),
[ASP.NET WebForms](https://www.syncfusion.com/jquery/aspnet-webforms-ui-controls?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples),
[JavaScript](https://www.syncfusion.com/javascript-ui-controls?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples),
[Angular](https://www.syncfusion.com/angular-ui-components?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples),
[React](https://www.syncfusion.com/react-ui-components?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples),
[Vue](https://www.syncfusion.com/vue-ui-components?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples),
and 
[Flutter](https://www.syncfusion.com/flutter-widgets?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples)),
mobile
([Xamarin](https://www.syncfusion.com/xamarin-ui-controls?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples),
[Flutter](https://www.syncfusion.com/flutter-widgets?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples),
[UWP](https://www.syncfusion.com/uwp-ui-controls?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples),
and
[JavaScript](https://www.syncfusion.com/javascript-ui-controls?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples)),
and desktop development ([Windows
Forms](https://www.syncfusion.com/winforms-ui-controls?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples),
[WPF](https://www.syncfusion.com/wpf-ui-controls?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples),
[WinUI(Preview)](https://www.syncfusion.com/winui-controls?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples),
[Flutter](https://www.syncfusion.com/flutter-widgets?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples)
and
[UWP](https://www.syncfusion.com/uwp-ui-controls?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples)).
We provide ready-to-deploy enterprise software for dashboards, reports,
data integration, and big data processing. Many customers have saved
millions in licensing fees by deploying our software.

		
<hr style="height:0.3px;border:none;color:lightgrey;background-color:lightgrey;" />

<p align="center">
  <a href="mailto:sales@syncfusion.com?Subject=Syncfusion Xamarin Autocomplete - Github" target="_top">sales@syncfusion.com</a> | <a href="https://www.syncfusion.com?utm_source=github&utm_medium=listing&utm_campaign=xamarin-autocomplete-github-samples">www.syncfusion.com</a> | 1-888-9 DOTNET <br>
</p>
