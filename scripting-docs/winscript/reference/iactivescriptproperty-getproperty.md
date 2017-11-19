---
title: IActiveScriptProperty::GetProperty | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScriptProperty.GetProperty
apilocation: scrobj.dll
helpviewer_keywords: GetProperty method, IActiveScriptProperty interface
ms.assetid: a43383db-b148-4d76-83bd-4f0e899b7cb1
caps.latest.revision: "24"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d55fb2d816931a74827d318e13860b3f97f0fd23
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptpropertygetproperty"></a>IActiveScriptProperty::GetProperty
Získá vlastnost, která je určena parametrem.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetProperty(  
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
 Hodnota vlastnosti získat.  
  
 `pvarIndex`  
 Nepoužívá se.  
  
 `pvarValue`  
 Hodnota vlastnosti  
  
 Povolené hodnoty pro `dwProperty` jsou popsané v následující tabulce.  
  
|Konstanta|Hodnota|Význam|  
|--------------|-----------|-------------|  
|SCRIPTPROP_INTEGERMODE|0x00003000|Vynutí skriptovací stroj k rozdělení v režimu celé číslo místo plovoucí režimu bodu.|  
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
 Vlastnost SCRIPTPROP_ABBREVIATE_GLOBALNAME_RESOLUTION hostitele slouží k informování skriptovací stroj, který neexistuje žádné skriptovacích strojů přispívání do globální objektu. Například může informovat Internet Exploreru [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] modul, který vykreslované stránky obsahuje pouze [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] skripty. Proto pouze [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] modul můžete přidat nové vlastnosti do okna objekt globální a není k dispozici žádný modul Visual Basic Scripting Edition (VBScript) o stejnou akci. Modul můžete ignorovat tento příznak nebo můžete použít k optimalizaci správu nové členy, které jsou přidány do globální objektu.  
  
 Hostitele můžete použít vlastnost SCRIPTPROP_INVOKEVERSIONING vyberte sadu funkcí jazyka být podporovaná, až [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] je skriptovací stroj spustil. Pokud je tato vlastnost nastavena na hodnotu 1 (SCRIPTLANGUAGEVERSION_5_7), k dispozici jazykové funkce jsou stejné jako ty, které se zobrazovaly ve verzi 5.7 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] skriptovacího stroje. Pokud je nastavena na hodnotu 2 (SCRIPTLANGUAGEVERSION_5_8), jsou k dispozici jazykové funkce ty, které se zobrazovaly ve verzi 5.7 Kromě funkcí, které byly přidány ve verzi 5.8. Ve výchozím nastavení je tato vlastnost nastavena na hodnotu 0 (SCRIPTLANGUAGEVERSION_DEFAULT), což je ekvivalentní sadu funkcí jazyka, který se objevil ve verzi 5.7, pokud hostitel podporuje různé výchozí chování. Pro instanci aplikace Internet Explorer 8 požádá do [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] jazykové funkce podporované verzí 5.8 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] skriptovací stroj ve výchozím nastavení při "Standardy aplikace Internet Explorer 8" režimu je režim dokumentu pro Internet Explorer 8.  
  
## <a name="see-also"></a>Viz také  
 [Definování kompatibility dokumentu](http://msdn.microsoft.com/library/cc288325)   
 [Iactivescriptproperty –](../../winscript/reference/iactivescriptproperty.md)   
 [Informace o verzi](../../javascript/reference/javascript-version-information.md)