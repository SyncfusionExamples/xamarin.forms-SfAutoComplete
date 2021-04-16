# xamarin.forms-SfAutoComplete
Initializing AutoComplete Import the SfAutoComplete namespace in respective Page as shown below:  XAML C#  xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms" Then initialize an empty autocomplete as shown below,  XAML C#  &lt;ContentPage xmlns="http://xamarin.com/schemas/2014/forms"              xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"              xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"              xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"              xmlns:local="clr-namespace:AutocompleteSample"              x:Class="AutocompleteSample.MainPage">     &lt;StackLayout          VerticalOptions="Start"          HorizontalOptions="Start"         Padding="30">         &lt;autocomplete:SfAutoComplete x:Name="autoComplete"                                      HeightRequest="40"/>     &lt;/StackLayout> &lt;/ContentPage> Populating AutoComplete with Data Now, let us create a simple list of country names and set it as the AutoCompleteSource of AutoComplete.  XAML C#  &lt;ContentPage xmlns="http://xamarin.com/schemas/2014/forms"              xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"              xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"              xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"              xmlns:local="clr-namespace:AutocompleteSample"              x:Class="AutocompleteSample.MainPage">     &lt;StackLayout          VerticalOptions="Start"          HorizontalOptions="Start"         Padding="30">         &lt;autocomplete:SfAutoComplete x:Name="autoComplete"                                      HeightRequest="40">             &lt;autocomplete:SfAutoComplete.AutoCompleteSource>                 &lt;ListCollection:List x:TypeArguments="x:String">                     &lt;x:String>India&lt;/x:String>                     &lt;x:String>Uganda&lt;/x:String>                     &lt;x:String>Ukraine&lt;/x:String>                     &lt;x:String>Canada&lt;/x:String>                     &lt;x:String>United Arab Emirates&lt;/x:String>                     &lt;x:String>France&lt;/x:String>                     &lt;x:String>United Kingdom&lt;/x:String>                     &lt;x:String>China&lt;/x:String>                     &lt;x:String>United States&lt;/x:String>                     &lt;x:String>Japan&lt;/x:String>                     &lt;x:String>Angola&lt;/x:String>                 &lt;/ListCollection:List>             &lt;/autocomplete:SfAutoComplete.AutoCompleteSource>         &lt;/autocomplete:SfAutoComplete>     &lt;/StackLayout> &lt;/ContentPage>
