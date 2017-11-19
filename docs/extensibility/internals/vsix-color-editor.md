---
title: Editor barva VSIX | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70879c5d-e0f0-4845-993c-2f4229869706
caps.latest.revision: "5"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7987d2b6d22893e82893755ed76fa5253aeb600c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="vsix-color-editor"></a>Editor barva VSIX
Nástroj editoru barva rozšíření Visual Studio můžete vytvářet a upravovat vlastní barvy pro sadu Visual Studio. Nástroj můžete také vygenerovat klíče motivů prostředků tak, aby barvy lze použít v kódu. Tento nástroj je užitečný pro provedení barvy pro rozšíření sady Visual Studio, který podporuje motivů. Tento nástroj můžete otevřít soubory .pkgdef a .xml. Visual Studio motivů (soubory .vstheme) lze pomocí editoru Visual Studio rozšíření barva změnou přípona souboru .xml. Kromě toho .vstheme soubory lze importovat do aktuální soubor .xml.  
  
 ![VSIX barva Editor nejdůležitější](../../extensibility/internals/media/vsix-color-editor-hero.png "nejdůležitější barva Editor VSIX")  
  
 **Definiční soubory balíčků**  
  
 (.Pkgdef) definiční soubory balíčků jsou soubory, které definují motivů. Barvy sami jsou uloženy v soubory XML barvu motivu, které jsou zkompilovány do souboru .pkgdef. Soubory .pkgdef jsou nasazené do umístění s možností vyhledávání sady Visual Studio, zpracovaných za běhu a sloučení definovat motivů.  
  
 **Barva tokeny**  
  
 Barva token se skládá ze čtyř prvků:  
  
-   **Název kategorie:** logické seskupení pro sadu barev. Použijte stávající název kategorie, pokud jsou již barev, které jsou specifické pro požadovaný element uživatelského rozhraní nebo skupině prvky uživatelského rozhraní.  
  
-   **Název tokenu:** popisný název pro barvu token a tokenu sady. Nastaví zahrnout pozadí a tokenu názvy popředí (text), stejně jako všechny stavy jejich, a to mít název, aby bylo snadné identifikovat dvojice a stavy, které se vztahují na.  
  
-   **Barva hodnoty (nebo odstíny):** potřebné pro každé barevný motiv. Vždy vytvořte textu a pozadí – hodnoty barev v párech. Barvy se daly párovat pro pozadí nebo popředí, tak, aby barvy (popředí) je vždy čitelná proti barvu pozadí, na kterém se nevykreslí. Tyto barvy jsou propojeny a se použije společně v uživatelském rozhraní. Pokud na pozadí není určen pro použití s textem, nedefinují barvu popředí.  
  
-   **Název systému barev:** pro použití v zobrazí vysokého kontrastu.  
  
## <a name="how-to-use-the-tool"></a>Postup použití nástroje  
 Co nejvíce, a případně by měl znovu použít existující sady Visual Studio barvy místo provedení nové. Však v případech, kde jsou definovány žádné odpovídající barvy, by se vytvořit vlastní barvy zachovat rozšíření motivů kompatibilní.  
  
 **Vytvoření nové tokeny barev**  
  
 Pokud chcete vytvořit vlastní barvy pomocí editoru Visual Studio rozšíření barvu, postupujte takto:  
  
1.  Určení názvů kategorie a token pro nové tokeny barev.  
  
2.  Zvolte odstíny, které element uživatelského rozhraní pro vysoký kontrast použije pro každý motiv a barvu systému.  
  
3.  Pomocí editoru barvu pro vytvoření nové tokeny barev.  
  
4.  Použijte barvy v rozšíření sady Visual Studio.  
  
5.  Testování v sadě Visual Studio.  
  
 **Krok 1: Stanovení kategorie a tokenu názvy pro nové tokeny barev.**  
  
 Upřednostňované pojmenování scheme VSColor je **[kategorie] [uživatelské rozhraní typ] [stavu]**. Nepoužívejte slovo "Barva" v názvech VSColor, jako je redundantní.  
  
 Názvy kategorií poskytují logické seskupení a by měl být definován jako úzce nejblíže. Například název časového období jednotný nástroj může být název kategorie, ale název týmu celý obchodní jednotky nebo projektu není. Seskupení položek do kategorií pomáhá zabránit záměně mezi barvy se stejným názvem.  
  
 Název tokenu musí označovat jasně typ elementu a situacích nebo "stavu," pro které se použijí barvu. Například aktivní data tip na **[uživatelského rozhraní typ]** by mohla mít název "**popis dat**" a **[stavu]** by mohla mít název "**Active**," výsledné v Barva název "**DataTipActive**." Vzhledem k tomu, že datové typy text, popředí a barvu pozadí musí být definované. Pomocí pozadí nebo popředí párování editoru barva automaticky vytvoří barvy "**DataTipActive**" pozadí a "**DataTipActiveText**" pro popředí.  
  
 Pokud je tímto druhem uživatelského rozhraní obsahuje pouze jeden stav, **[stavu]** lze vynechat část názvu. Například pokud má vyhledávací pole ohraničení a neexistuje žádná změna stavu, které má vliv na barvu ohraničení,, pak název pro token barvu ohraničení je jednoduše nelze volat "**SearchBoxBorder**."  
  
 Některé běžné názvy stavu patří:  
  
-   Aktivní  
  
-   Neaktivní  
  
-   Myš nad  
  
-   MouseDown –  
  
-   Vybrané  
  
-   Zaměřuje  
  
 Příklady několik názvů tokenu pro části ovládacího prvku seznam položek:  
  
-   ListItem  
  
-   ListItemBorder  
  
-   ListItemMouseOver  
  
-   ListItemMouseOverBorder  
  
-   ListItemSelected  
  
-   ListItemSelectedBorder  
  
-   ListItemDisabled  
  
-   ListItemDisabledBorder  
  
 **Krok 2: Zvolte odstíny, které element uživatelského rozhraní pro vysoký kontrast použije pro každý motiv a barvu systému.**  
  
 Při výběru vlastních barev pro uživatelské rozhraní, vyberte podobné existující prvek uživatelského rozhraní a použít jako základ jeho barvy. Barvy pro prvky uživatelského rozhraní ve pole projít kontrolní a testování, tak budou vypadat příslušné a chovat správně ve všech motivů.  
  
 **Krok 3: Použití editoru barvu k vytvoření nové tokeny barev.**  
  
 Spusťte editor barva a otevřete nebo vytvořte nový soubor .xml barvy vlastní motiv. Vyberte **Upravit > novou barvu** z nabídky. Otevře se dialogové okno pro zadání kategorii a jeden nebo více názvů pro barvu položky v rámci této kategorie:  
  
 ![VSIX barva Editor novou barvu](../../extensibility/internals/media/vsix-color-editor-new-color.png "novou barvu barva Editor VSIX")  
  
 Zvolte existující kategorii nebo vyberte **novou kategorii** vytvořte novou kategorii. Otevře se dialogové okno jiný, vytváření název nové kategorie:  
  
 ![VSIX barva Editor novou kategorii](../../extensibility/internals/media/vsix-color-editor-new-category.png "novou kategorii barva Editor VSIX")  
  
 Nové kategorie pak budou k dispozici ve **novou barvu** kategorie rozevírací nabídce. Po výběru kategorie, zadejte jeden název na každý řádek pro každý nový token barva a vyberte možnost "Vytvořit" po dokončení:  
  
 ![VSIX barva Editor novou barvu vyplněno](../../extensibility/internals/media/vsix-color-editor-new-color-filled.png "VSIX barva Editor novou barvu vyplněno")  
  
 Barevné hodnoty jsou zobrazeny v párech pozadí nebo popředí s "Žádný" indikující, že barvu nebyla definována. Poznámka: Pokud barvu, která nemá text barvu nebo pozadí pár barvu, pak jenom na pozadí musí být definován.  
  
 ![Barva Editor VSIX – hodnoty barev](../../extensibility/internals/media/vsix-color-editor-color-values.png "barva Editor VSIX – hodnoty barev")  
  
 Chcete-li upravit token barvu, vyberte položku barvu pro motiv (sloupec) tohoto tokenu. Přidejte hodnotu barvu zadáním šestnáctkových barva hodnotu ve formátu ARGB 8 číslic, zadání názvu barvy systému do buňky, nebo pomocí rozevírací nabídky vyberte požadovanou barvu přes sadu posuvníky nebo seznam barev systému.  
  
 ![Barva upravit barvy Editor VSIX](../../extensibility/internals/media/vsix-color-editor-edit-color.png "VSIX barva Editor upravit barvy")  
  
 ![VSIX Editor barvu pozadí](../../extensibility/internals/media/vsix-color-editor-background.png "VSIX Editor barvu pozadí")  
  
 Pro součásti, které není nutné zobrazit text, zadejte hodnotu pouze jednu barvu: barvu pozadí. Jinak zadejte hodnoty pro barvu textu a pozadí, oddělených lomítkem.  
  
 Při zadávání hodnot pro vysoký kontrast, zadejte platné názvy barvy systému Windows. Nezadávejte pevně zakódované ARGB hodnoty. Seznam názvů barva platný systému můžete zobrazit výběrem "Pozadí: systém" nebo "Systém popředí:" z rozevíracích nabídek Barva hodnotu. Při vytváření prvky, které mají textové komponenty, použijte pár barva systému správné pozadí nebo textu nebo text může nečitelná.  
  
 Po dokončení vytváření, nastavení a úpravy tokeny barvu, je uložte do požadovaného .xml nebo .pkgdef formátu. Barva tokeny s ani pozadí ani sadu popředí bude uložena jako prázdný barvy ve formátu .xml ale zahozena ve formátu .pkgdef. Zobrazí se dialogové okno upozornění, potenciální ztráty barva Pokud budete chtít uložit do souboru .pkgdef prázdný barvy.  
  
 **Krok 4: Použití barvy v rozšíření sady Visual Studio.**  
  
 Po definování barvu nové tokeny, zahrnout .pkgdef v souboru projektu "Sestavení Action" nastavena na "Obsah" a "Zahrnují v VSIX" nastavena na hodnotu "True".  
  
 ![Editor barva VSIX pkgdef](../../extensibility/internals/media/vsix-color-editor-pkgdef.png "Editor barva VSIX pkgdef")  
  
 V editoru Visual Studio rozšíření barvu, zvolte Soubor > Zobrazit kód prostředků k zobrazení kód, který se používá pro přístup k vlastní barvy v uživatelském rozhraní grafického subsystému WPF.  
  
 ![Prohlížeč kód prostředku barva Editor VSIX](../../extensibility/internals/media/vsix-color-editor-resource-code-viewer.png "prohlížeč kód prostředku barva Editor VSIX")  
  
 Zahrňte tento kód statické třídy v projektu. Odkaz na **Microsoft.VisualStudio.Shell.\< VSVersion >.0.dll** se musí přidat k projektu pro použití **ThemeResourceKey** typu.  
  
```csharp  
namespace MyCustomColors  
{  
    public static class MyCategory  
    {  
        #region Autogenerated resource keys  
        // These resource keys are generated by Visual Studio Extension Color Editor, and should be replaced when new colors are added to this category.  
        public static readonly Guid Category = new Guid("faf7f3f9-9fe5-4dd3-9350-59679617dfbe");  
  
        private static ThemeResourceKey _MyColor1ColorKey;  
        private static ThemeResourceKey _MyColor1BrushKey;  
        private static ThemeResourceKey _MyColor1TextColorKey;  
        private static ThemeResourceKey _MyColor1TextBrushKey;  
        public static ThemeResourceKey MyColor1ColorKey { get { return _MyColor1ColorKey ?? (_MyColor1ColorKey = new ThemeResourceKey(Category, "MyColor1", ThemeResourceKeyType.BackgroundColor)); } }  
        public static ThemeResourceKey MyColor1BrushKey { get { return _MyColor1BrushKey ?? (_MyColor1BrushKey = new ThemeResourceKey(Category, "MyColor1", ThemeResourceKeyType.BackgroundBrush)); } }  
        public static ThemeResourceKey MyColor1TextColorKey { get { return _MyColor1TextColorKey ?? (_MyColor1TextColorKey = new ThemeResourceKey(Category, "MyColor1", ThemeResourceKeyType.ForegroundColor)); } }  
        public static ThemeResourceKey MyColor1TextBrushKey { get { return _MyColor1TextBrushKey ?? (_MyColor1TextBrushKey = new ThemeResourceKey(Category, "MyColor1", ThemeResourceKeyType.ForegroundBrush)); } }  
        #endregion  
    }  
}  
```  
  
 To umožňuje přístup k barev v kódu jazyka XAML a umožňuje rozhraní reagovat na změny motivu.  
  
```xaml  
<UserControl x:Class="NewTestProject.TestPackageControl" Name="MyToolWindow"  
             xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
             xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
             xmlns:ns="clr-namespace:MyCustomColors">  
  <Grid>  
    <TextBlock Background="{DynamicResource {x:Static ns:MyCategory.MyColor1BrushKey}}"  
               Foreground="{DynamicResource {x:Static ns:MyCategory.MyColor1TextBrushKey}}"  
      >Sample Text</TextBlock>  
  
  </Grid>  
</UserControl>  
```  
  
 **Krok 5: Testování v sadě Visual Studio.**  
  
 Barva editor, můžete použít dočasně barva tokeny pro spuštěné instance sady Visual Studio, chcete-li zobrazit změny barvy v za provozu bez nutnosti opětovného sestavení balíčku rozšíření. Uděláte to tak, klikněte na tlačítko "Vztahuje tento motiv s windows v sadě Visual Studio" nachází na záhlaví sloupce každý motiv. Toto dočasný motiv zmizí při zavření editoru VSIX barev.  
  
 ![Použít Editor barva VSIX](../../extensibility/internals/media/vsix-color-editor-apply.png "použít Editor barva VSIX")  
  
 Chcete-li provedené změny trvalé, sestavili a nasadili rozšíření sady Visual Studio, po přidání nových barev do souboru .pkgdef a psaní kódu, který bude používat tyto barvy. Opětovné sestavení rozšíření sady Visual Studio dojde ke sloučení hodnoty registru pro nové barvy do zbytku motivy. Pak znovu spusťte Visual Studio, zobrazení uživatelského rozhraní a ověřte, že nové barvy zobrazují podle očekávání.  
  
## <a name="notes"></a>Poznámky  
 Tento nástroj je určen pro použití pro vytváření vlastních barev pro motivy dříve existující sady Visual Studio, nebo pro úpravy barvy vlastní motiv sady Visual Studio. Chcete-li vytvořit úplný vlastní motivy sady Visual Studio, stáhněte [rozšíření Visual Studio barvu motivu editoru](http://visualstudiogallery.msdn.microsoft.com/6f4b51b6-5c6b-4a81-9cb5-f2daa560430b) z Galerie rozšíření sady Visual Studio.  
  
## <a name="sample-output"></a>Vzorový výstup  
 **Barva výstup XML**  
  
 Soubor .xml, který je generovaný nástrojem bude podobná této:  
  
```xml  
<Themes>  
  <Theme Name="Light" GUID="{de3dbbcd-f642-433c-8353-8f1df4370aba}">  
    <Category Name="CategoryName" GUID="{eee9d521-dac2-48d9-9a5e-5c625ba2040c}">  
      <Color Name="ColorName1">  
        <Background Type="CT_RAW" Source="FFFFFFFF" />  
      </Color>  
      <Color Name="ColorName2">  
        <Background Type="CT_RAW" Source="FFFFFFFF" />  
        <Foreground Type="CT_RAW" Source="FF000000" />  
      </Color>  
      <Color Name="ColorName3">  
        <Background Type="CT_RAW" Source="FFFF0000" />  
      </Color>  
      <Color Name="ColorName4">  
        <Background Type="CT_RAW" Source="FF000088" />  
        <Foreground Type="CT_RAW" Source="FFFFFFFF" />  
      </Color>  
    </Category>  
  </Theme>  
  <Theme Name="Dark" GUID="{1ded0138-47ce-435e-84ef-9ec1f439b749}">...</Theme>  
  <Theme Name="Blue" GUID="{a4d6a176-b948-4b29-8c66-53c97a1ed7d0}">...</Theme>  
  <Theme Name="HighContrast" GUID="{a5c004b4-2d4b-494e-bf01-45fc492522c7}">...</Theme>  
</Themes>  
  
```  
  
 **Výstup PKGDEF barev**  
  
 Soubor .pkgdef generovaný nástrojem bude podobná této:  
  
```  
[$RootKey$\Themes\{de3dbbcd-f642-433c-8353-8f1df4370aba}\CategoryName]  
"Data"=hex:78,00,00,00,0b,00,00,00,01,00,00,00,21,d5,e9,ee,c2,da,d9,48,9a,5e,5c,62,5b,a2,04,0c,04,00,00,00,0a,00,00,00,43,6f,6c,6f,72,4e,61,6d,65,31,01,ff,ff,ff,ff,00,0a,00,00,00,43,6f,6c,6f,72,4e,61,6d,65,32,01,ff,ff,ff,ff,01,00,00,00,ff,0a,00,00,00,43,6f,6c,6f,72,4e,61,6d,65,33,01,ff,00,00,ff,00,0a,00,00,00,43,6f,6c,6f,72,4e,61,6d,65,34,01,00,00,88,ff,01,ff,ff,ff,ff  
[$RootKey$\Themes\{1ded0138-47ce-435e-84ef-9ec1f439b749}\CategoryName]  
"Data"=hex:...  
[$RootKey$\Themes\{a4d6a176-b948-4b29-8c66-53c97a1ed7d0}\CategoryName]  
"Data"=hex:...  
[$RootKey$\Themes\{a5c004b4-2d4b-494e-bf01-45fc492522c7}\CategoryName]  
"Data"=hex:...  
  
```  
  
 **Obálka klíče prostředků C#**  
  
 Barva prostředků klíče generovaný nástrojem bude podobná této:  
  
```csharp  
namespace MyNamespace  
{  
    public static class MyColors  
    {  
        #region Autogenerated resource keys  
        // These resource keys are generated by Visual Studio Extension Color Editor, and should be replaced when new colors are added to this category.  
  
        public static string ColorName1ColorKey { get { return "ColorName1ColorKey"; } }  
        public static string ColorName1BrushKey { get { return "ColorName1BrushKey"; } }  
  
        public static string ColorName2ColorKey { get { return "ColorName2ColorKey"; } }  
        public static string ColorName2BrushKey { get { return "ColorName2BrushKey"; } }  
        public static string ColorName2TextColorKey { get { return "ColorName2TextColorKey"; } }  
        public static string ColorName2TextBrushKey { get { return "ColorName2TextBrushKey"; } }  
  
        public static string ColorName3ColorKey { get { return "ColorName4ColorKey"; } }  
        public static string ColorName3BrushKey { get { return "ColorName4BrushKey"; } }  
        public static string ColorName3TextColorKey { get { return "ColorName4TextColorKey"; } }  
        public static string ColorName3TextBrushKey { get { return "ColorName4TextBrushKey"; } }  
        #endregion  
    }  
}  
```  
  
 **Obálka slovník prostředků WPF**  
  
 Barva **ResourceDictionary** klíče generovaný nástrojem bude podobná této:  
  
```xaml  
<ResourceDictionary xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:colors="clr-namespace:MyNamespace">  
  
  <SolidColorBrush x:Key="{x:Static colors:MyColors.ColorName1BrushKey}" Color="#FFFFFFFF" />  
  <Color x:Key="{x:Static colors:MyColors.ColorName1ColorKey}" A="255" R="255" G="255" B="255" />  
  
  <SolidColorBrush x:Key="{x:Static colors:MyColors.ColorName2BrushKey}" Color="#FFFFFFFF" />  
  <Color x:Key="{x:Static colors:MyColors.ColorName2ColorKey}" A="255" R="255" G="255" B="255" />  
  <SolidColorBrush x:Key="{x:Static colors:MyColors.ColorName2TextBrushKey}" Color="#FF000000" />  
  <Color x:Key="{x:Static colors:MyColors.ColorName2TextColorKey}" A="255" R="0" G="0" B="0" />  
  
  <SolidColorBrush x:Key="{x:Static colors:MyColors.ColorName3BrushKey}" Color="#FFFF0000" />  
  <Color x:Key="{x:Static colors:MyColors.ColorName3ColorKey}" A="255" R="255" G="0" B="0" />  
  
  <SolidColorBrush x:Key="{x:Static colors:MyColors.ColorName4BrushKey}" Color="#FF000088" />  
  <Color x:Key="{x:Static colors:MyColors.ColorName4ColorKey}" A="255" R="0" G="0" B="136" />  
  <SolidColorBrush x:Key="{x:Static colors:MyColors.ColorName4TextBrushKey}" Color="#FFFFFFFF" />  
  <Color x:Key="{x:Static colors:MyColors.ColorName4TextColorKey}" A="255" R="255" G="255" B="255" />  
</ResourceDictionary>  
```