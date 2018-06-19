---
title: GetObject – funkce (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- GetObject
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- GetObject function
ms.assetid: 62efcdbc-8b86-491d-9000-ef38aa9942a9
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0d8bad127a0f260395a1ec19f44ff2d495006024
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790746"
---
# <a name="getobject-function-javascript"></a>GetObject – funkce (JavaScript)
Vrátí odkaz na objekt automatizace ze souboru.  
  
> [!NOTE]
>  Tato funkce není podporována v aplikaci Internet Explorer 9 (režim standardů) nebo novější.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
GetObject([pathname] [, class])  
```  
  
## <a name="parameters"></a>Parametry  
 `pathname`  
 Volitelné. Úplná cesta a název souboru, který obsahuje objekt, který chcete načíst. Pokud `pathname` je vynechán, `class` je vyžadován.  
  
 `class`  
 Volitelné. Třída objektu.  
  
 `class` Argument používá syntaxi `appname.objectype` a má následující části:  
  
 `appname`  
 Požadováno. Název aplikace poskytnutím tohoto objektu.  
  
 `objectype`  
 Požadováno. Typ nebo třídu objektu. Chcete-li vytvořit.  
  
## <a name="remarks"></a>Poznámky  
 `GetObject` Funkce není podporována v [!INCLUDE[jsv9text](../../javascript/includes/jsv9text-md.md)] nebo novější.  
  
 Použití `GetObject` funkce, která má přístup k objektu automatizace ze souboru. Přiřaďte objekt vrácený `GetObject` proměnnou objektu. Příklad:  
  
```JavaScript  
var CADObject;  
CADObject = GetObject("C:\\CAD\\SCHEMA.CAD");  
```  
  
 Při spuštění tohoto kódu, aplikaci přidruženou k zadané `pathname` spuštění a aktivaci objektu do zadaného souboru. Pokud `pathname` obsahuje řetězec nulové délky (""), `GetObject` vrátí novou instanci objektu zadaného typu. Pokud `pathname` je argument vynechán, `GetObject` vrací aktuálně aktivní objekt zadaného typu. Pokud žádný objekt zadaného typu neexistuje, dojde k chybě.  
  
 Některé aplikace umožňují aktivovat část souboru. Uděláte to tak, přidejte na konec názvu souboru vykřičníkem (!) a po ní následuje řetězec, který identifikuje část souboru, který chcete aktivovat. Informace o tom, jak vytvořit tento řetězec, najdete v dokumentaci k aplikaci, která vytvořila objekt.  
  
 Například v kreslení aplikace může mít více vrstev do výkresu uložené v souboru. Můžete použít následující kód k aktivaci vrstvy v rámci výkresu s názvem `SCHEMA.CAD`:  
  
```JavaScript  
var LayerObject = GetObject("C:\\CAD\\SCHEMA.CAD!Layer3");  
```  
  
 Pokud nezadáte třídu objektu, automatizace Určuje, která aplikace spustit a které objekt, který chcete aktivovat, na základě názvu souboru, který zadáte. Některé soubory, ale může podporovat více než jednu třídu objektu. Například výkresu může podporovat tři různé typy objektů: objekt aplikace, objekt kreslení a objekt nástrojů, které jsou součástí stejného souboru. Chcete-li určit, který objekt v souboru, kterou chcete aktivovat, použijte nepovinný `class` argument. Příklad:  
  
```JavaScript  
var MyObject;  
MyObject = GetObject("C:\\DRAWINGS\\SAMPLE.DRW", "FIGMENT.DRAWING");  
```  
  
 V předchozím příkladu `FIGMENT` je název kreslení aplikace a `DRAWING` je jeden z typů objektů podporuje. Po aktivaci objektu, který odkazujete v kódu pomocí definované proměnné objektu. V předchozím příkladu přístup k vlastnosti a metody nového objektu pomocí objektové proměnné `MyObject`. Příklad:  
  
```JavaScript  
MyObject.Line(9, 90);  
MyObject.InsertText(9, 100, "Hello, world.");  
MyObject.SaveAs("C:\\DRAWINGS\\SAMPLE.DRW");  
```  
  
> [!NOTE]
>  Použití `GetObject` fungovat, pokud je aktuální instanci objektu, nebo pokud chcete vytvořit objekt s soubor již načten. Pokud není žádná aktuální instance a nechcete, aby objekt začít s načíst soubor, použijte `ActiveXObject` objektu.  
  
 Pokud objekt zaregistroval jako objekt jedné instance, jenom jeden objekt se vytvoří instance, bez ohledu na to, jak tolikrát, kolikrát `ActiveXObject` se spustí. S jednou instancí objektu `GetObject` vždy vrátí stejné instanci při volání s řetězec nulové délky ("") syntaxe a dojde k chybě, pokud `pathname` je tento argument vynechán.  
  
## <a name="requirements"></a>Požadavky  
 Podporováno v následujících režimech dokumentů: Quirks, standardy aplikace Internet Explorer 6, standardy aplikace Internet Explorer 7 a standardy aplikace Internet Explorer 8. Viz [Informace o verzi](../../javascript/reference/javascript-version-information.md).  
  
## <a name="see-also"></a>Viz také  
 [Activexobject – objekt](../../javascript/reference/activexobject-object-javascript.md)