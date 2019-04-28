---
title: Pomocné metody textových šablon | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- text templates, utility methods
ms.assetid: 8c11f9f7-678b-4f0c-b634-dc78fda699d1
caps.latest.revision: 52
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 0da69de4a91ebabce4af99e26195b349ef5daa60
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63411412"
---
# <a name="text-template-utility-methods"></a>Pomocné metody textových šablon
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Existuje několik metod, které jsou vám k dispozici vždy při psaní kódu [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] textové šablony. Tyto metody jsou definovány v <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation>.  
  
> [!TIP]
> Můžete také použít jiné metody a služby poskytované hostitelské prostředí v běžné šablony textu (ne Předzpracované). Například můžete vyřešit cesty k souborům, protokolování chyb a získat služby poskytované [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] a načíst všechny balíčky.  Další informace najdete v tématu [přístup k sadě Visual Studio z textové šablony](http://msdn.microsoft.com/0556f20c-fef4-41a9-9597-53afab4ab9e4).  
  
## <a name="write-methods"></a>Zápis metod  
 Můžete použít `Write()` a `WriteLine()` metody přidat text uvnitř bloku standardní kódu, namísto použití bloku kódu výrazu. Následující bloky kódu dva jsou funkčně ekvivalentní.  
  
##### <a name="code-block-with-an-expression-block"></a>Blok kódu pomocí blok výrazu  
  
```  
<#  
int i = 10;  
while (i-- > 0)  
    { #>  
        <#= i #>  
    <# }  
#>  
```  
  
##### <a name="code-block-using-writeline"></a>Blok kódu pomocí WriteLine()  
  
```  
<#   
    int i = 10;  
    while (i-- > 0)  
    {   
        WriteLine((i.ToString()));  
    }  
#>  
```  
  
 Vám může být užitečné používat jednu z těchto metod nástroj namísto blok výrazu dovnitř bloku kódu long s vnořené řídicí struktury.  
  
 `Write()` a `WriteLine()` metody mají dvě přetížení, ten, který přijímá jako parametr jeden řetězec a ten, který má složený řetězec formátu plus pole objektů, které chcete zahrnout do řetězce (například `Console.WriteLine()` metoda). Následující dva výskyty `WriteLine()` jsou funkčně ekvivalentní:  
  
```  
<#  
    string msg = "Say: {0}, {1}, {2}";  
    string s1 = "hello";  
    string s2 = "goodbye";  
    string s3 = "farewell";  
  
    WriteLine(msg, s1, s2, s3);  
    WriteLine("Say: hello, goodbye, farewell");  
#>   
```  
  
## <a name="indentation-methods"></a>Odsazení metody  
 Odsazení metody můžete použít k formátování výstupu textové šablony. <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation> Třída nemá `CurrentIndent` řetězci, který ukazuje aktuálním odsazení v textové šabloně a `indentLengths` pole, který je seznam odsazení, které byly přidány. Přidáte odsazení s `PushIndent()` metoda a odečítání odsazení s `PopIndent()` metody. Pokud chcete odebrat všechny odsazení, použijte `ClearIndent()` metody. Následující blok kódu ukazuje použití těchto metod:  
  
```  
<#  
    WriteLine(CurrentIndent + "Hello");  
    PushIndent("    ");  
    WriteLine(CurrentIndent + "Hello");  
    PushIndent("    ");  
    WriteLine(CurrentIndent + "Hello");  
    ClearIndent();  
    WriteLine(CurrentIndent + "Hello");  
    PushIndent("    ");  
    WriteLine(CurrentIndent + "Hello");  
#>  
```  
  
 Tento blok kódu vytvoří následující výstup:  
  
```  
Hello  
        Hello  
                Hello  
Hello  
        Hello  
```  
  
## <a name="error-and-warning-methods"></a>Chyby a upozornění metody  
 Chybové a výstražné pomocné metody slouží k přidání zprávy [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] seznam chyb. Například následující kód přidá chybovou zprávu do seznamu chyb.  
  
```  
<#  
  try  
  {  
    string str = null;  
    Write(str.Length.ToString());  
  }  
  catch (Exception e)  
  {  
    Error(e.Message);  
  }  
#>    
```  
  
## <a name="access-to-host-and-service-provider"></a>Přístup k hostiteli a poskytovatele služeb  
 Vlastnost `this.Host` může poskytnout přístup k vlastnostem zveřejněným hostitelem, který spouští šablony. Použití `this.Host`, je nutné nastavit `hostspecific` atribut `<@template#>` – direktiva:  
  
 `<#@template ... hostspecific="true" #>`  
  
 Typ `this.Host` závisí na typu host, ve kterém je spuštěn šablony. V šabloně, která běží v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], můžete přetypovat `this.Host` k `IServiceProvider` k získání přístupu ke službám, jako integrované vývojové prostředí. Příklad:  
  
```  
EnvDTE.DTE dte = (EnvDTE.DTE) ((IServiceProvider) this.Host)  
                       .GetService(typeof(EnvDTE.DTE));  
```  
  
## <a name="using-a-different-set-of-utility-methods"></a>Použití různých sadu pomocných metod  
 Jako součást procesu generování text, soubor šablony se transformuje na třídu, která je vždy pojmenováno `GeneratedTextTransformation`a dědí z <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation>. Pokud chcete použít jinou sadu metod, místo toho můžete napsat vlastní třídu a je zadat v direktivě šablony. Vaše třída musí dědit z <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation>.  
  
```  
<#@ template inherits="MyUtilityClass" #>  
```  
  
 Použití `assembly` směrnice odkazovat na sestavení, kde lze nalézt zkompilované třídy.
