---
title: IActiveScriptProperty::SetProperty | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IActiveScriptProperty.SetProperty
apilocation:
- scrobj.dll
helpviewer_keywords:
- SetProperty method, IActiveScriptProperty interface
ms.assetid: 0ba429c5-04a3-4505-bc5f-69c505dfca91
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bc9b5f4c0d02789988bb41f46417651414beed7f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptpropertysetproperty"></a>IActiveScriptProperty::SetProperty
Nastaví vlastnost, která je určena parametrem.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT SetProperty(  
// The property value:  
    uint dwProperty,    
// Not used:   
    IntPtr pvarIndex,    
// The value of the property:   
    out object pvarValue,    
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwProperty`  
 Hodnota vlastnosti, kterou chcete nastavit.  
  
 `pvarIndex`  
 Nepoužívá se.  
  
 `pvarValue`  
 Hodnota vlastnosti  
  
 Povolené hodnoty pro `dwProperty` jsou popsané v následující tabulce.  
  
|Konstanta|Hodnota|Význam|  
|--------------|-----------|-------------|  
|SCRIPTPROP_INTEGERMODE|0x00003000|Vynutí skriptovací stroj k rozdělení v režimu celé číslo místo plovoucí režimu bodu. Výchozí hodnota je `False`.|  
|SCRIPTPROP_STRINGCOMPAREINSTANCE|0x00003001|Povoluje funkce Porovnat řetězec skriptovací stroje, které mají být nahrazeny.|  
|SCRIPTPROP_ABBREVIATE_GLOBALNAME_RESOLUTION|0x70000002|Informuje o skriptovací stroj, který neexistuje žádné skriptovacích strojů přispívání do globální objektu.|  
|SCRIPTPROP_INVOKEVERSIONING|0x00004000|Vynutí [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] skriptovací stroj pro výběr sady funkcí jazyk podporovaný. Výchozí sadu funkcí jazyka podporovaných [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] skriptovací stroj je ekvivalentní sadu funkcí jazyka, který se objevil ve verzi 5.7 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] skriptovacího stroje.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí jednu z následujících hodnot:  
  
|Návratová hodnota|Význam|  
|------------------|-------------|  
|`S_OK`|Úspěch.|  
|`E_INVALIDARG`|Argument není platný.|  
|`E_UNEXPECTED`|Nebyl očekáván volání (například skriptovací stroj ještě byla načtena nebo inicializovat).|  
  
## <a name="remarks"></a>Poznámky  
 K povolení nebo zakázání dělení celého čísla, vyvolání `SetProperty` a proveďte převod `Boolean` k `Object`. Ve výchozím nastavení, hodnota vlastnosti je `False`. Pokud je nastavena na `True`, operace dělení vrátí jenom celá čísla.  
  
 K povolení nebo zakázání porovnání vlastním řetězcem, vyvolání `SetProperty` a předat `Object` hodnotu. Objekt, který můžete předat musí implementovat rozhraní [iactivescriptstringcompare – rozhraní](../../winscript/reference/iactivescriptstringcompare-interface.md). [StrComp](../../winscript/reference/iactivescriptstringcompare-strcomp.md) metodu [iactivescriptstringcompare – rozhraní](../../winscript/reference/iactivescriptstringcompare-interface.md) rozhraní je volána při každém provedení funkce Porovnat řetězec.  
  
 Vyberte sadu funkcí jazyka ke podporované, když [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] skriptovací stroj je inicializován, vyvolání `SetProperty` a předejte hodnotu, která odpovídá do sady povolit u SCRIPTPROP_INVOKEVERSIONING funkcí jazyka. Pokud je tato vlastnost nastavena na hodnotu 1 (SCRIPTLANGUAGEVERSION_5_7), k dispozici jazykové funkce jsou stejné jako ty, které se zobrazovaly ve verzi 5.7 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] skriptovacího stroje. Pokud je nastavena na hodnotu 2 (SCRIPTLANGUAGEVERSION_5_8), jsou k dispozici jazykové funkce ty, které se zobrazovaly ve verzi 5.7 Kromě nových funkcí, které byly přidány ve verzi 5.8. Ve výchozím nastavení je tato vlastnost nastavena na hodnotu 0 (SCRIPTLANGUAGEVERSION_DEFAULT), což je ekvivalentní sadu funkcí jazyka, který se objevil ve verzi 5.7, pokud hostitel podporuje různé výchozí chování. Například aplikace Internet Explorer 8 požádá do [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] jazykové funkce, které jsou podporovány verze 5.8 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] skriptovací stroj ve výchozím nastavení při "Standardy aplikace Internet Explorer 8" režim je výchozí režim dokumentu pro Internet Explorer 8. Přepínání režim dokumentu aplikace Internet Explorer 8 pro Internet Explorer 7, režim standardů nebo režim adaptivní resetuje [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] skriptovací stroj pro podporu pouze funkce sadu jazyk, které existovalo v na verzi 5.7 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] skriptovacího stroje.  
  
> [!NOTE]
>  SCRIPTPROP_INVOKEVERSIONING by mělo být nastavené pouze tehdy, když [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] inicializace skriptovacího stroje.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak vynutit skriptovacího stroje používat celočíselné dělení a o tom, aby přetížení funkce porovnání.  
  
```c#  
BMLScriptEngine bmlScriptEngine = new BMLScriptEngine();  
IActiveScriptProperty scriptProperties = bmlScriptEngine as   
    IActiveScriptProperty;  
  
// Force the scripting engine to use integer division.  
Boolean enableIntegerDivision = true;  
Object vtIntegerDivInstance = (Object)enableIntegerDivision;  
                scriptProperties.SetProperty(SCRIPTPROP_INTEGERDIVISION,   
    System.IntPtr.Zero, ref vtIntegerDivInstance);  
  
// Allow overloading of the compare function.  
BMLScriptStringCompare bmlScriptStringCompareInstance = new   
    BMLScriptStringCompare();  
Object vtStrCmpInstance = (Object)bmlScriptStringCompareInstance;  
scriptProperties.SetProperty(SCRIPTPROP_STRCOMPINST,   
    System.IntPtr.Zero, ref vtStrCmpInstance);  
```  
  
## <a name="see-also"></a>Viz také  
 [Definování kompatibility dokumentu](http://msdn.microsoft.com/library/cc288325)   
 [Iactivescriptproperty –](../../winscript/reference/iactivescriptproperty.md)   
 [Informace o verzi](../../javascript/reference/javascript-version-information.md)