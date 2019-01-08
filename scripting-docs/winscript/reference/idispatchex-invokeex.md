---
title: IDispatchEx::InvokeEx | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispatchEx.InvokeEx
apilocation:
- scrobj.dll
helpviewer_keywords:
- InvokeEx method
ms.assetid: d90783e6-4b89-4423-8a56-a9c8b4b2c813
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e631ecca1181a25fa3cf419f5fc96666f0db3cd6
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086525"
---
# <a name="idispatchexinvokeex"></a>IDispatchEx::InvokeEx
Poskytuje přístup k vlastnostem a metodám vystaveným podle `IDispatchEx` objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT InvokeEx(  
   DISPID id,  
   LCID lcid,  
   WORD wFlags,  
   DISPARAMS *pdp,  
   VARIANT *pVarRes,   
   EXCEPINFO *pei,   
   IServiceProvider *pspCaller   
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `id`  
 Identifikuje člena. Používá `GetDispID` nebo `GetNextDispID` získat identifikátor odeslání.  
  
 `lcid`  
 Kontext národního prostředí pro interpretaci argumentů. `lcid` Je předán `InvokeEx` umožňující objektu pro interpretaci argumentů specifické pro národní prostředí.  
  
 `wFlags`  
 Právní hodnoty `wFlags` jsou:  
  
 DISPATCH_PROPERTYGET &AMP;#124; DISPATCH_METHOD &AMP;#124; DISPATCH_PROPERTYPUT &AMP;#124; DISPATCH_PROPERTYPUTREF &AMP;#124; DISPATCH_CONSTRUCT  
  
 Příznaky popisující kontext `InvokeEx` volání:  
  
|Hodnota|Význam|  
|-----------|-------------|  
|DISPATCH_METHOD|Člen je vyvolána jako metodu. Pokud je vlastnost se stejným názvem, lze nastavit to a příznak DISPATCH_PROPERTYGET (definované `IDispatch`).|  
|DISPATCH_PROPERTYGET|Člen je načíst, protože vlastnost nebo datový člen (definované `IDispatch`).|  
|DISPATCH_PROPERTYPUT|Člen se změní jako vlastnost nebo datový člen (definované `IDispatch`).|  
|DISPATCH_PROPERTYPUTREF|Člen se změní přiřazení odkazu spíše než přiřazení hodnoty. Tento příznak je platný pouze v případě, že vlastnost přijímá odkaz na objekt (definované `IDispatch`).|  
|DISPATCH_CONSTRUCT|Člen se používá jako konstruktor. (Toto je nová hodnota určené `IDispatchEx`). Právní hodnoty `wFlags` jsou:<br /><br /> DISPATCH_PROPERTYGET DISPATCH_METHOD DISPATCH_PROPERTYPUT DISPATCH_PROPERTYPUTREF DISPATCH_CONSTRUCT|  
  
 `pdp`  
 Ukazatel na strukturu obsahující matici argumentů, pole DISPID pro pojmenované argumenty a počty prvků v polích. Zobrazit `IDispatch` dokumentaci úplný popis DISPPARAMS struktury.  
  
 `pVarRes`  
 Ukazatel na umístění, kde se výsledek uložené nebo hodnotu Null, pokud volající nepředpokládá žádný výsledek. Tento argument se ignoruje, pokud je zadána DISPATCH_PROPERTYPUT nebo DISPATCH_PROPERTYPUTREF.  
  
 `pei`  
 Ukazatel na strukturu, která obsahuje informace o výjimce. Tato struktura by mělo být vyplněno if `DISP_E_EXCEPTION` je vrácena. Může mít hodnotu Null. Najdete v článku `IDispatch` dokumentaci pro úplný popis `EXCEPINFO` struktury.  
  
 `pspCaller`  
 Ukazatel na objekt poskytovatele služeb poskytovaných volajícího, který umožňuje objekt, který chcete získat služby od volajícího. Může mít hodnotu Null.  
  
 `IDispatchEx::InvokeEx` poskytuje všechny stejné funkce jako `IDispatch::Invoke` a přidá několik rozšíření:  
  
|||  
|-|-|  
|DISPATCH_CONSTRUCT|Označuje, že položka je používán jako konstruktor.|  
|`pspCaller`|`pspCaller` Umožňuje přístup k objektům na služby poskytované volající. Určité služby může zpracovat volající sama nebo delegovat na volajícím, které si řetěz volání. Například pokud skriptovací stroj v prohlížeči provede `InvokeEx` můžete postupovat podle volání externí objekt objektu `pspCaller` řetězu získat services z skriptovací stroj nebo prohlížeč. (Všimněte si, že řetěz volání, který není stejný jako řetěz vytváření – označované také jako kontejner řetězec nebo řetězec lokality. Vytvoření řetězce může být k dispozici další mechanismem, jako `IObjectWithSite`.)|  
|`this` Ukazatel|Pokud je DISPATCH_METHOD nastavená `wFlags`, může být "pojmenovaným parametrem" pro hodnotu "Tento". Hodnota DISPID bude DISPID_THIS a musí být první pojmenovaným parametrem.|  
  
 Nevyužité `riid` parametr `IDispatch::Invoke` byla odebrána.  
  
 `puArgArr` Parametr `IDispatch::Invoke` byla odebrána.  
  
 Zobrazit `IDispatch::Invoke` dokumentaci v následujících příkladech:  
  
 "Volání metody bez argumentů."  
  
 "Získání a nastavení vlastnosti"  
  
 "Předávání parametrů"  
  
 "Indexované vlastnosti"  
  
 "Vyvolání výjimky během Invoke"  
  
 "Vrací chyby"  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí jednu z následujících hodnot:  
  
|||  
|-|-|  
|`S_OK`|Úspěch.|  
|DISP_E_BADPARAMCOUNT|Počet prvků poskytnuté DISPPARAMS se liší od počtu argumentů přijal metody nebo vlastnosti.|  
|DISP_E_BADVARTYPE|Jeden z argumentů v `rgvarg` není platný typ variant.|  
|DISP_E_EXCEPTION|Aplikace je potřeba vyvolat výjimku. V tomto případě struktura předaná `pei` by mělo být vyplněno.|  
|DISP_E_MEMBERNOTFOUND|Požadovaný člen neexistuje, nebo volání `InvokeEx` se pokusila nastavit hodnotu vlastnosti jen pro čtení.|  
|DISP_E_NONAMEDARGS|Tato implementace `IDispatch` nepodporuje pojmenované argumenty.|  
|DISP_E_OVERFLOW|Jeden z argumentů v `rgvarg` nelze převést na zadaný typ.|  
|DISP_E_PARAMNOTFOUND|Jeden z parametrů hodnoty dispID neodpovídá parametru u metody.|  
|DISP_E_TYPEMISMATCH|Jeden nebo více argumentů se neshoduje.|  
|DISP_E_UNKNOWNLCID|Člen vyvolání interpretuje řetězec argumenty podle LCID, a identifikátor LCID nebyl rozpoznán. Pokud LCID není nutná pro interpretaci argumentů, by neměl vrátil tuto chybu.|  
|DISP_E_PARAMNOTOPTIONAL|Byl vynechán požadovaný parametr.|  
  
## <a name="example"></a>Příklad  
  
```cpp
VARIANT var;  
   BSTR bstrName;  
   DISPID dispid;  
   IDispatchEx *pdex;  
   DISPPARAMS dispparamsNoArgs = {NULL, NULL, 0, 0};  
  
   // Assign to pdex and bstrName  
   if (SUCCEEDED(pdex->GetDispID(bstrName, fdexNameCaseSensitive, &dispid)))  
   {  
      pdex->InvokeEx(dispid, LOCALE_USER_DEFAULT,  
         DISPATCH_PROPERTYGET, &dispparamsNoArgs,   
         &var, NULL, NULL);  
   }  
```  
  
## <a name="see-also"></a>Viz také  
 [IDispatchEx – rozhraní](../../winscript/reference/idispatchex-interface.md)   
 [IDispatchEx::GetDispID](../../winscript/reference/idispatchex-getdispid.md)   
 [IDispatchEx::GetNextDispID](../../winscript/reference/idispatchex-getnextdispid.md)