---
title: Hierarchie typů symbolů třídy | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- symbols [DIA SDK], class hierarchies
ms.assetid: 0ccd6990-4654-44cd-a6f3-bdd82fe90f6c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 66bada6b1c1f0a925277fcc1716659ba431c35d8
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55039959"
---
# <a name="class-hierarchy-of-symbol-types"></a>Hierarchie tříd typů symbolů
Následující tabulka popisuje typy symbolu v hierarchii tříd.  
  
## <a name="symbol-types"></a>Typů symbolů  
  
|Typ symbolu|Popis|  
|-----------------|-----------------|  
|[UDT](../../debugger/debug-interface-access/udt.md)|Symbol použitý k reprezentaci jednotlivých třídy, struktury a sjednocení.|  
|[Výčet (Přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/enum-debug-interface-access-sdk.md)|Symbol pro výčtové typy.|  
|[PointerType](../../debugger/debug-interface-access/pointertype.md)|Symbol pro typy ukazatelů.|  
|[ArrayType](../../debugger/debug-interface-access/arraytype.md)|Symbol pro typy polí.|  
|[BaseType](../../debugger/debug-interface-access/basetype.md)|Symbol pro základní typy|  
|[Typedef (Přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/typedef-debug-interface-access-sdk.md)|Symbol, který představuje názvy pro ostatní typy.|  
|[BaseClass](../../debugger/debug-interface-access/baseclass.md)|Symbolu používanou pro každou základní třídu uživatelem definovaný typ (UDT).|  
|[Friend (Přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/friend-debug-interface-access-sdk.md)|Symbol spřátelené třídy a funkce friend.|  
|[FunctionType](../../debugger/debug-interface-access/functiontype.md)|Symbol pro každou jedinečnou funkci podpis.|  
|[FunctionArgType](../../debugger/debug-interface-access/functionargtype.md)|Symbol pro každý parametr funkce.|  
|[VTableShape](../../debugger/debug-interface-access/vtableshape.md)|Symbol pro velikost virtuální tabulky.|  
|[VTable](../../debugger/debug-interface-access/vtable.md)|Symbol pro virtuální tabulky.|  
|[CustomType](../../debugger/debug-interface-access/customtype.md)|Symbol pro typ definované dodavatelem.|  
|[ManagedType](../../debugger/debug-interface-access/managedtype.md)|Symbol pro typ definovaný v metadatech.|  
|[Rozměr](../../debugger/debug-interface-access/dimension.md)|Symbol rozměry pole.|  
  
> [!NOTE]
>  Každý symbol může mít vlastnosti, které obsahují informace o symbolu, jakož i odkazy na jiné symboly. Tyto vlastnosti jsou uvedeny v tématech pro jednotlivé symbol.  
  
## <a name="see-also"></a>Viz také  
 [CV_access_e Enumeration](../../debugger/debug-interface-access/cv-access-e.md)   
 [Lexikální hierarchie typů symbolů](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [Symboly a značky symbolů](../../debugger/debug-interface-access/symbols-and-symbol-tags.md)