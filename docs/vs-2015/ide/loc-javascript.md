---
title: '&lt;loc&gt; (JavaScript) | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- <loc> JavaScript XML tag
- loc JavaScript XML tag
ms.assetid: 0d3349b6-4bdd-418f-bc11-73665305baae
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 8029dc6282e7b5a4ff9075257bcb1b6213a4a6b4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54758522"
---
# <a name="ltlocgt-javascript"></a>&lt;loc&gt; (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Určuje umístění a typ souboru sajdkára, která obsahuje lokalizované informace technologie IntelliSense.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<loc filename="filename"  
    format="vsdoc|messagebundle" />  
```  
  
#### <a name="parameters"></a>Parametry  
 `filename`  
 Volitelné. Název kořenové sajdkára souboru, který obsahuje informace o lokalizaci pro neutrální jazykovou verzi. Když Visual Studio vyhledá informace o lokalizaci, pokusí se najít verzi specifické pro jazykovou verzi tohoto souboru. Například pokud `filename` je jquery.xml, Visual Studio vyhledá správné složky specifické pro jazykovou verzi (například JA) ve stejném umístění jako soubor .js, který obsahuje `<loc>` elementu. Pokud je možné vyhledat složky specifické pro jazykovou verzi, zkontroluje, jestli existuje soubor jquery.xml v ní. Pokud nemůže najít správný soubor, místo toho používá pravidla pro umístění spravovaných prostředků. Výchozí hodnota pro `filename` je název aktuálního souboru, ale s příponou .xml místo js.  
  
 `format`  
 Volitelné. Typ souboru sajdkára používají pro lokalizaci. Použít `messagebundle` určit sady zprávy určené otevřít Ajax metadat. `messagebundle` je doporučeným formátem. Ale tento formát není podporován v Microsoft Ajax nebo soubory .winmd. Použití `vsdoc` k určení formátu Standardní lokalizace rozhraní .NET Framework, který používá Microsoft Ajax a prostředí Windows Runtime. Tento atribut je volitelný. `vsdoc` je výchozí formát.  
  
## <a name="remarks"></a>Poznámky  
 `<loc>` Elementu musí být uvedena v horní části souboru ve stejném oddílu jako `<reference>` elementu. Použití pravidel pro `<loc>` element jsou stejné jako `<reference>` elementu. Další informace najdete v části "Odkazy na direktivy" v [technologie IntelliSense jazyka JavaScript](../ide/javascript-intellisense.md).  
  
 Visual Studio zpracovává jeden `<loc>` – element pro každý soubor .js. Pokud je položek víc `<loc>` prvky jsou k dispozici, pouze jeden `<loc>` element se používá. Chování při určování `<loc>` není definován prvek, který chcete použít.  
  
 Při použití formátu sady prostředků, použijte `locid` atribut v dokumentační komentáře XML k určení `name` hodnotu atributu.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `<loc>` element s messagebundle formátu. Přidejte následující kód XML do souboru s názvem messageFilename.xml a umístěte ho do správné složky specifické pro jazykovou verzi, jak je uvedeno v popisu `filename` parametru.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<messagebundle>  
  <msg name="1">A class that represents a rectangle</msg>  
  <msg name="2">The height of a rectangle</msg>  
  <msg name="3">The width of a rectangle</msg>  
</messagebundle>  
  
```  
  
 Například messagebundle přidejte následující kód do souboru jazyka JavaScript ve vašem projektu. `<loc>` Elementu musí být uvedená jako první řádek v souboru jazyka JavaScript. Popisy v tomto kódu se nahradí lokalizované popisy, pokud je k dispozici.  
  
```javascript  
/// <loc filename="messageFilename.xml" format="messagebundle"/>  
  
function doSomething(a,b)   
{  
    /// <summary locid='1'>description</summary>  
    /// <param name='a' locid='2'>parameter a description</param>  
    /// <param name='b' locid='3'>parameter b description</param>  
}  
  
```  
  
 Následující příklad používá VSDoc formátu. Přidejte následující kód XML do souboru s názvem scriptFilename.xml a umístěte ho do správné složky specifické pro jazykovou verzi.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<doc>  
  <assembly>  
    <name>Lights</name>  
  </assembly>  
  <members>  
    <member name="M:illuminate">  
      <summary>Activates a light. </summary>  
      <param name='a'>The light to activate. </param>  
    </member>  
  </members>  
</doc>  
  
```  
  
 Například VSDoc přidejte následující kód do souboru jazyka JavaScript ve vašem projektu. Popisy v tomto kódu se nahradí lokalizované popisy, pokud je k dispozici.  
  
```javascript  
/// <loc filename="scriptFilename.xml" format="vsdoc" />  
  
function illuminate(a)   
{  
    /// <summary locid='M:illuminate'>description</summary>  
    /// <param name='a' type='Number'>parameter a description</param>  
}  
  
```  
  
## <a name="see-also"></a>Viz také  
 [Dokumentační komentáře XML](../ide/xml-documentation-comments-javascript.md)
