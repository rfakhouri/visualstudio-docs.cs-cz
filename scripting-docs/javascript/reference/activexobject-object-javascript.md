---
title: "Activexobject – objekt (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ActiveXObject
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- ActiveXObject object
- Automation objects, ActiveXObject objects
ms.assetid: 9c7bed07-853f-48aa-92db-3131324746ec
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 77bb743aeab563f7d7711e4caa9a0fcf0b45ff58
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="activexobject-object-javascript"></a>ActiveXObject – objekt (JavaScript)
Povolí a vrátí odkaz na automatizační objekt.  
  
 Tento objekt slouží pouze k vytvoření instancí automatizačních objektů a nemá žádné členy.  
  
> [!WARNING]
>  Tento objekt je rozšíření Microsoft a je podporovaná v aplikaci Internet Explorer, není ve [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
newObj = new ActiveXObject(servername.typename[, location])  
```  
  
## <a name="parameters"></a>Parametry  
 `newObj`  
 Požadováno. Název proměnné, do kterého `ActiveXObject` je přiřazen.  
  
 `servername`  
 Požadováno. Název aplikace poskytující objekt.  
  
 `typename`  
 Požadováno. Typ nebo třída objektu, které se mají vytvořit.  
  
 `location`  
 Volitelné. Název síťového serveru, na kterém má být objekt vytvořen.  
  
## <a name="remarks"></a>Poznámky  
 Automatizační servery poskytují alespoň jeden typ objektu. Například aplikace pro zpracování textu může poskytovat objekt aplikace, objekt dokumentu a objekt panelu nástrojů.  
  
 Bude pravděpodobně možné identifikovat `servername.typename` hodnoty na hostiteli v počítači `HKEY_CLASSES_ROOT` klíč registru. Následují příklady hodnot, na které můžete narazit v závislosti na tom, jaké programy jsou nainstalovány:  
  
-   Excel.Application  
  
-   Excel.Chart  
  
-   Scripting.FileSystemObject  
  
-   WScript.Shell  
  
-   Word.Document  
  
> [!IMPORTANT]
>  Objekty ActiveX mohou způsobovat potíže se zabezpečením. Použít `ActiveXObject`, budete muset upravit nastavení zabezpečení v Internet Exploreru pro zónu zabezpečení relevantní. Například pro zónu místního intranetu je obvykle třeba změnit vlastní nastavení na „Inicializace a ovládací prvky skriptu ActiveX nejsou označeny jako bezpečné pro skriptování“.  
  
 K identifikaci členů automatizace objektu, který můžete použít ve vašem kódu, možná muset použít Prohlížeč objektů COM, jako [Prohlížeč objektů OLE/COM](http://msdn.microsoft.com/library/d0kh9f4c.aspx), pokud žádná referenční dokumentace je k dispozici pro objekt automatizace.  
  
 Chcete-li vytvořit objekt automatizace, přiřadit nové `ActiveXObject` proměnné objektu:  
  
```JavaScript  
var ExcelApp = new ActiveXObject("Excel.Application");  
var ExcelSheet = new ActiveXObject("Excel.Sheet");  
```  
  
 Tento kód spustí aplikaci, která vytváří objekt (v tomto případě list aplikace Microsoft Excel). Jakmile je objekt vytvořen, je na něj v kódu odkazováno pomocí definované proměnné objektu. V následujícím příkladu je přístup k vlastnosti a metody nového objektu pomocí objektové proměnné `ExcelSheet` a dalších objektů aplikace Excel, včetně objekt aplikace a kolekce ActiveSheet.Cells.  
  
```JavaScript  
// Make Excel visible through the Application object.  
ExcelSheet.Application.Visible = true;  
// Place some text in the first cell of the sheet.  
ExcelSheet.ActiveSheet.Cells(1,1).Value = "This is column A, row 1";  
// Save the sheet.  
ExcelSheet.SaveAs("C:\\TEST.XLS");  
// Close Excel with the Quit method on the Application object.  
ExcelSheet.Application.Quit();  
```  
  
## <a name="requirements"></a>Požadavky  
 Podporováno v následujících režimech dokumentů: adaptivní, režim standardů aplikace Internet Explorer 6, režim standardů aplikace Internet Explorer 7, režim standardů aplikace Internet Explorer 8, režim standardů aplikace Internet Explorer 9, režim standardů aplikace Internet Explorer 10, režim standardů aplikace Internet Explorer 11. Není podporováno v [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace. Viz [Informace o verzi](../../javascript/reference/javascript-version-information.md).  
  
> [!NOTE]
>  Vytvoření `ActiveXObject` na vzdáleném serveru není podporována v [!INCLUDE[jsv9text](../../javascript/includes/jsv9text-md.md)] nebo novější.  
  
## <a name="see-also"></a>Viz také  
 [GetObject – funkce](../../javascript/reference/getobject-function-javascript.md)   
 [Jedinečný ověřování pomocí Magic HTML5 nebo WCF ukázkové aplikace](http://code.msdn.microsoft.com/Unique-Authentication-f32d2da0)