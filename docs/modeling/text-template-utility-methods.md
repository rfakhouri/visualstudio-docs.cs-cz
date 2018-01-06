---
title: "Pomocné metody textových šablon | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: text templates, utility methods
ms.assetid: 8c11f9f7-678b-4f0c-b634-dc78fda699d1
caps.latest.revision: "50"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: cff244ea8b3ba8e6dd25af06d51bf5b80b51aa06
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="text-template-utility-methods"></a>Pomocné metody textových šablon
Existuje několik metod, které jsou k dispozici vždy při psaní kódu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] textové šablony. Tyto metody jsou definovány v <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation>.  
  
> [!TIP]
>  Můžete také použít jiné metody a služeb poskytovaných hostitelské prostředí v pravidelných (ne předběžně zpracované) textové šablony. Například můžete vyřešit cesty k souborům, protokolování chyb a získat služeb poskytovaných [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a všechny načíst balíčky.  Další informace najdete v tématu [přístup k sadě Visual Studio z textové šablony](http://msdn.microsoft.com/en-us/0556f20c-fef4-41a9-9597-53afab4ab9e4).  
  
## <a name="write-methods"></a>Zápis metod  
 Můžete použít `Write()` a `WriteLine()` metody připojit text v rámci bloku standardní kódu namísto použití bloku kódu výrazu. Následující bloky kódu dva jsou funkčně rovnocenné.  
  
##### <a name="code-block-with-an-expression-block"></a>Blok kódu s bloku výraz  
  
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
  
 Možná bude vhodné použít jednu z těchto metod nástroj místo bloku výraz uvnitř bloku dlouho kódu s vnořené řídicí struktury.  
  
 `Write()` a `WriteLine()` metody mají dva přetížení, ten, který přebírá parametr jednoho řetězce a jeden, který přebírá složený formátovací řetězec a pole objektů, které chcete zahrnout do řetězce (jako `Console.WriteLine()` metoda). Následující dva použití `WriteLine()` stejné funkce:  
  
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
 Odsazení metody slouží k formátování výstupu z textové šablony. <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation> Třída má `CurrentIndent` řetězec vlastnost, která zobrazuje aktuální odsazení v textové šablony a `indentLengths` pole tedy seznam odsazení, které byly přidány. Můžete přidat odsazení s `PushIndent()` metoda a odečítání odsazení s `PopIndent()` metoda. Pokud chcete odebrat všechny odsazení, použijte `ClearIndent()` metoda. Následující blok kódu ukazuje použití těchto metod:  
  
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
 Chybové a výstražné pomocné metody můžete přidat zprávy a pokuste se [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] seznam chyb. Následující kód například přidá chybovou zprávu do seznamu chyb.  
  
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
 Vlastnost `this.Host` může poskytnout přístup k vlastnosti vystavené hostitele, který provádí šablony. Použít `this.Host`, je nutné nastavit `hostspecific` atribut `<@template#>` – direktiva:  
  
 `<#@template ... hostspecific="true" #>`  
  
 Typ `this.Host` závisí na typ hostitele, ve kterém je prováděna šablony. V šabloně, který běží v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], může odevzdat `this.Host` k `IServiceProvider` k získání přístupu k službám, jako je rozhraní IDE. Příklad:  
  
```  
EnvDTE.DTE dte = (EnvDTE.DTE) ((IServiceProvider) this.Host)  
                       .GetService(typeof(EnvDTE.DTE));  
```  
  
## <a name="using-a-different-set-of-utility-methods"></a>Pomocí jiné sady pomocné metody  
 Jako součást procesu generování textu souboru šablony převede na třídu, která je vždy s názvem `GeneratedTextTransformation`a dědí z <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation>. Pokud chcete použít jiné metody sada místo toho můžete napsat vlastní třídu a zadejte jej v – direktiva šablony. Třídě musí dědit z <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation>.  
  
```  
<#@ template inherits="MyUtilityClass" #>  
```  
  
 Použití `assembly` direktivu pro odkaz sestavení, které lze nalézt zkompilované třídy.