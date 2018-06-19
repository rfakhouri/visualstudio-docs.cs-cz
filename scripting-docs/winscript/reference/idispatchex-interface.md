---
title: IDispatchEx – rozhraní | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDispatchEx interface, about IDispatchEx
- IDispatchEx interface
ms.assetid: 37a3303f-f78e-4b5b-aac8-b836c92819de
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9a100a193f5e3abcb076fb8aaf3d64a0d0c38833
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24795243"
---
# <a name="idispatchex-interface"></a>IDispatchEx – rozhraní
`IDispatchEx`, rozšíření `IDispatch` rozhraní, podporuje funkce vhodné pro dynamické jazyků, například skriptovací jazyky. Tato část popisuje `IDispatchEx` rozhraní samostatně, rozdíly mezi `IDispatch` a `IDispatchEx`a důvody tohoto rozšíření. Očekává se, že čtečky obeznámeni s `IDispatch` a mají přístup ke `IDispatch` dokumentaci.  
  
## <a name="remarks"></a>Poznámky  
 `IDispatch`byla vyvinuta v podstatě pro Microsoft Visual Basic. Primární omezení `IDispatch` je, že předpokládá, že se objekty statické. Jinými slovy protože objekty neměňte během doby běhu, informace o typu můžete plně popisují je v době kompilace. Dynamické běhové modely, které se nacházejí v skriptovací jazyky, jako je například Visual Basic Scripting Edition (VBScript) a [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] a objekt modely, jako je Dynamic HTML vyžadují flexibilnější rozhraní.  
  
 `IDispatchEx`byl vyvinut poskytnout všechny služby `IDispatch` a také některé rozšíření, které jsou vhodné pro dynamičtější pozdní vazbou jazyků, například skriptovací jazyky. Další funkce `IDispatchEx` nad rámec `IDispatch` jsou:  
  
-   Přidat nové členy k objektu ("expando") – použijte `GetDispID` s `fdexNameEnsure` příznak.  
  
-   Odstranit členům v objektu – použít `DeleteMemberByName` nebo `DeleteMemberByDispID`.  
  
-   Malá a velká písmena výstupních operací – použít `fdexNameCaseSensitive` nebo `fdexNameCaseInsensitive`.  
  
-   Vyhledejte člen s názvem implicitní – použijte `fdexNameImplicit`.  
  
-   Zobrazení výčtu hodnoty dispID objektu – použijte `GetNextDispID`.  
  
-   Mapa ze DISPID pro název elementu – použijte `GetMemberName`.  
  
-   Získat vlastnosti objektu členů – použijte `GetMemberProperties`.  
  
-   Volání metody s `this` ukazatel – použít `InvokeEx` s DISPATCH_METHOD.  
  
-   Povolit prohlížeče, které podporují koncept obory názvů získat název místa nadřazeného objektu – použijte `GetNameSpaceParent`.  
  
 Objektů, které podporují `IDispatchEx` může také podporovat `IDispatch` z důvodu zpětné kompatibility. Dynamické povaha objekty, které podporují `IDispatchEx` má několik důsledky pro `IDispatch` rozhraní těchto objektů. Například `IDispatch` nepředpokládá následující:  
  
-   Člen a parametr musí zůstat hodnoty dispID konstantní po dobu jeho existence objektu. To umožňuje klientům získat hodnoty dispID jednou a ukládat je do mezipaměti pro pozdější použití.  
  
 Vzhledem k tomu `IDispatchEx` umožňuje přidání a odstranění členů sadu platné hodnoty dispID zůstanou není konstantní. Ale `IDispatchEx` vyžaduje, že mapování mezi DISPID a člen název zůstat konstantní. To znamená, že pokud dojde k odstranění člen:  
  
-   DISPID nemůže znovu, dokud nebude vytvořen člen se stejným názvem.  
  
-   DISPID musí zůstat platné pro `GetNextDispID`.  
  
-   DISPID musí přijmout řádně podle těchto sloupců `IDispatch` nebo `IDispatchEx` metody – musí rozpoznat člena, protože odstraněny a vrátí odpovídající chybový kód (obvykle DISP_E_MEMBERNOTFOUND nebo S_FALSE).  
  
## <a name="examples"></a>Příklady  
 To [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] kód v test() funkce provede následující akce:  
  
-   Vytvoří nový objekt voláním `Object` konstruktor a přiřadí ukazatel na nový objekt k proměnné objektu vývoz.  
  
-   Vytvoří nového elementu s názvem Elem v objektu a přiřadí do tohoto elementu ukazatel na funkci cat.  
  
-   Volání této funkce. Vzhledem k tomu, že se nazývá jako metodu, `this` ukazatel odkazuje na objekt objektu vývoz. Funkce přidá nového elementu řádku, aby se objekt.  
  
 Úplný kód HTML je:  
  
```  
<html>  
<body>  
<script type="text/javascript">  
function cat()  
{  
   // Create new element and assign the value 10  
   this.Bar = 10;  
}  
  
function test()  
{  
   // Construct new object  
   Obj = new Object();  
  
   // Create new element and assign function pointer  
   Obj.Elem = cat;  
  
   // Call Elem method ("this" == Obj)  
   Obj.Elem();  
  
   // Obj.Bar now exists  
}  
test();  
</script>  
</body>  
</html>  
```  
  
 Prvek řízení umístěný na této stejné webové stránce může získat odesílání ukazatel k skriptovacích strojů ukládaných z prohlížeče. Ovládací prvek pak může implementovat test() funkce:  
  
```  
<html>  
<body>  
<script type="text/javascript">  
function cat()  
{  
   // Create new element and assign the value 10  
   this.Bar = 10;  
}  
</script>  
<object id="test" <CLASSID="CLSID:9417DB5D-FA2A-11D0-8CB3-00C04FC2B085">>  
</object>  
</body>  
</html>  
```  
  
 Kód z ovládacího prvku, testování, má stejnou funkci jako [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] funkce `test()`. Všimněte si, že tyto odesílání volání do spuštění [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] modul a ke změně stavu modulu:  
  
-   Získá odesílání ukazatele na funkce pomocí cat `GetDispID()`.  
  
-   Získá odesílání ukazatele na funkce pomocí objektu `GetDispID()`.  
  
-   Vytvoří objekt voláním funkce objektu se `InvokeEx()` a získá odesílání ukazatel na nově vytvořený objekt.  
  
-   Vytvoří nového elementu, Elem, v objektu pomocí `GetDispID()` s `fdexNameEnsure` příznak.  
  
-   Vloží odesílání ukazatele na cat v elementu pomocí `InvokeEx()`.  
  
-   Volání odesílání ukazatel na cat jako metodu voláním `InvokeEx()` a předání v odesílání ukazatele konstruovaný objekt, jako `this` ukazatel.  
  
-   Metoda cat vytvoří nového elementu panelu na aktuální `this` objektu.  
  
-   Ověřuje, že nového elementu panelu, byl vytvořen v konstruovaný objekt výčet prostřednictvím elementů pomocí `GetNextDispID()`.  
  
 Kód pro ovládací prvek testu:  
  
```  
   BOOL test(IDispatchEx *pdexScript)  
   {  
      HRESULT hr;  
      VARIANT var;  
      DISPID dispid, putid;  
      BOOL retval = FALSE;  
      BSTR bstrName = NULL;  
      IDispatch   *pdispObj = NULL, *pdispCat = NULL;  
      IDispatchEx *pdexObj = NULL;  
      DISPPARAMS dispparams, dispparamsNoArgs = {NULL, NULL, 0, 0};  
  
      // Get dispatch pointer for "cat"  
      bstrName = SysAllocString(OLESTR("cat"));  
         if (bstrName == NULL) goto LDone;  
      hr = pdexScript->GetDispID(bstrName, 0, &dispid);  
         if (FAILED(hr)) goto LDone;  
      SysFreeString(bstrName);  
         bstrName = NULL;  
      hr = pdexScript->InvokeEx(dispid, LOCALE_USER_DEFAULT,   
         DISPATCH_PROPERTYGET, &dispparamsNoArgs,   
         &var, NULL, NULL);  
         if (FAILED(hr)) goto LDone;  
      pdispCat = var.pdispVal;  
  
      // Create object by calling "Object" constructor  
      bstrName = SysAllocString(OLESTR("Object"));  
         if (NULL == bstrName) goto LDone;  
      hr = pdexScript->GetDispID(bstrName, 0, &dispid);  
         if (FAILED(hr)) goto LDone;  
      SysFreeString(bstrName);  
         bstrName = NULL;  
      hr = pdexScript->InvokeEx(dispid, LOCALE_USER_DEFAULT,   
         DISPATCH_CONSTRUCT, &dispparamsNoArgs,   
         &var, NULL, NULL);  
         if (FAILED(hr)) goto LDone;  
      pdispObj = var.pdispVal;  
      hr = pdispObj->QueryInterface(IID_IDispatchEx, (void **)&pdexObj);  
         if (FAILED(hr)) goto LDone;  
  
      // Create new element in object  
      bstrName = SysAllocString(OLESTR("Elem"));  
         if (NULL == bstrName) goto LDone;  
      hr = pdexObj->GetDispID(bstrName, fdexNameEnsure, &dispid);  
         if (FAILED(hr)) goto LDone;  
      SysFreeString(bstrName);  
         bstrName = NULL;  
  
      // Assign "cat" dispatch pointer to element  
      putid = DISPID_PROPERTYPUT;  
      var.vt = VT_DISPATCH;  
      var.pdispVal = pdispCat;  
      dispparams.rgvarg = &var;  
      dispparams.rgdispidNamedArgs = &putid;  
      dispparams.cArgs = 1;  
      dispparams.cNamedArgs = 1;  
      hr = pdexObj->InvokeEx(dispid, LOCALE_USER_DEFAULT,   
         DISPATCH_PROPERTYPUTREF, &dispparams,  
         NULL, NULL, NULL);  
         if (FAILED(hr)) goto LDone;  
  
      // Invoke method with "this" pointer  
      putid = DISPID_THIS;  
      var.vt = VT_DISPATCH;  
      var.pdispVal = pdispObj;  
      dispparams.rgvarg = &var;  
      dispparams.rgdispidNamedArgs = &putid;  
      dispparams.cArgs = 1;  
      dispparams.cNamedArgs = 1;  
      hr = pdexObj->InvokeEx(dispid, LOCALE_USER_DEFAULT,  
         DISPATCH_METHOD, &dispparams,  
            NULL, NULL, NULL);  
         if (FAILED(hr)) goto LDone;  
  
      // Confirm that new element "Bar" is in object  
      hr = pdexObj->GetNextDispID(fdexEnumAll, DISPID_STARTENUM, &dispid);  
      while (hr == NOERROR)  
      {  
            hr = pdexObj->GetMemberName(dispid, &bstrName);  
            if (FAILED(hr)) goto LDone;  
            retval = !wcscmp(bstrName, OLESTR("Bar"));  
            SysFreeString(bstrName);  
            bstrName = NULL;  
            if (retval) goto LDone;  
         hr = pdexObj->GetNextDispID(fdexEnumAll, dispid, &dispid);  
      }  
LDone:  
   SysFreeString(bstrName);  
   if (pdispCat != NULL)  
      pdispCat->Release();  
   if (pdispObj != NULL)  
      pdispObj->Release();  
   if (pdexObj != NULL)  
      pdexObj->Release();  
  
   return retval;  
   }  
```  
  
## <a name="methods"></a>Metody  
 [IDispatchEx – metody](../../winscript/reference/idispatchex-methods.md)