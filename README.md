# Rapport

## Välkommen till MyAmazingApp!

```
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    ...
    <uses-permission android:name="android.permission.INTERNET" />
    ...
</manifest>
```
Appen har fått tillgång till internet i filen "AndroidManifest.xml", vilket gör att kan besöka högskolan i Skövde 
och min webbsida med hjälp av externa och interna webbsidor. Detta visas ovanför koden.

```
<WebView
        android:id="@+id/my_webview"
        ... />
```
En WebView-element med id "my_webview" har skapats i filen "activity_main.xml" som visas ovanför koden. 

```
...
private WebView myWebView;

@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    ...
    // locate my_webview id and instantiate.
    myWebView = findViewById(R.id.my_webview);
    ...
}
...
```
Det finns en method i "MainActivity.java" som söker efter id "my_webview" i "activity_main.xml" 
och sedan returerar värdet som lagras i en privat medlem variabel "myWebView". Detta visas ovanför koden.

```
...
private WebView myWebView;

@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    ...
    // webViewClient allows us to browse the web inside our app.
    myWebView.setWebViewClient(new WebViewClient()); // Do not open in Chrome!
    // Enable Javascript execution in your WebViewClient
    myWebView.getSettings().setJavaScriptEnabled(true);
    ...
}
...
```
Det finns också en method "setWebViewClient" med en parameter "WebViewClient" som gör att bläddra på webben 
och aktiverar JavaScript för att kunna integrera med webbsidan. Detta visas ovanför koden.

```
...
public void showExternalWebPage(){
    // TODO: Add your code for showing external web page here
    myWebView.loadUrl("https://his.se");
}

public void showInternalWebPage(){
    // TODO: Add your code for showing internal web page here
    myWebView.loadUrl("file:///android_asset/code/index.html");
}
...
```
Det finns en meny i appen som låter användaren välja mellan "External Web Page" eller "Internal Web Page". 
För att implementera detta skapas två funktioner som heter "showExternalWebPage" och "showInternalWebPage".
"showExternalWebPage" tar användaren till högskolan i Skövdes webbsida, medan "showInternalWebPage" tar användaren till min webbsida. Detta visas ovanför koden.

![img.png](img.png)
Så här ser ut när externa webbsida används som visas ovanför bilden.

![img_1.png](img_1.png)
Så här ser ut när interna webbsida används som visas ovanför bilden.

# Fördelar 
- Appen har tillgång till JavaScipt, vilekt gör att intergara med webbsidor som kan vara en meny med många funktioner.
- Appen är enken att använda eftersom den inte har många funktioner eller för mycket element i appen.
- Appen är gratis och kan laddas ner direkt från min kod. Om ni vill kan ni supporta till mig för att förbättra appen 
och få tidig tillgång till nya versioner när de släpps.

# Nackdelar 
- Appen har tillgång till javascipt, men kan också introducera sårbarheter, vilket innebär att risken för att bli hackad om appen används.
- Just nu kan appen endast användas för två webbsidor som är högskolan i Skövde och min webbsida, men appen är förstätt en prototyp som innebär att den kan ha fler webbsidor.
- Appen är fortfarande är en prototyp kan den skapa på problem som krascher, programfrysningar eller säkerhetsproblem.

Läs gärna:

- Boulos, M.N.K., Warren, J., Gong, J. & Yue, P. (2010) Web GIS in practice VIII: HTML5 and the canvas element for interactive online mapping. International journal of health geographics 9, 14. Shin, Y. &
- Wunsche, B.C. (2013) A smartphone-based golf simulation exercise game for supporting arthritis patients. 2013 28th International Conference of Image and Vision Computing New Zealand (IVCNZ), IEEE, pp. 459–464.
- Wohlin, C., Runeson, P., Höst, M., Ohlsson, M.C., Regnell, B., Wesslén, A. (2012) Experimentation in Software Engineering, Berlin, Heidelberg: Springer Berlin Heidelberg.
