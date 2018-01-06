---
title: "Idiasymbol::get_undecoratednameex – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol::get_undecoratedNameEx method
ms.assetid: 579aed0b-c57d-41a1-a94a-3bf665fd4a9d
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 82d0b25b2306cc957015ec4c205a22cd44660357
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolgetundecoratednameex"></a>IDiaSymbol::get_undecoratedNameEx
Načte část nebo všechny bez upraveného název jazyka C++ dekorované název (propojení).  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_undecoratedNameEx(   
   DWORD undecorateOptions,  
   BSTR* pRetval  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `undecoratedOptions`  
 [v] Určuje kombinaci příznaky, řídíte, co je vrácen. Najdete v části poznámky pro konkrétní hodnoty a co dělají.  
  
 `pRetVal`  
 [out] Vrátí že název dekorované upraveného název jazyka C++.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` nebo chybový kód.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená vlastnost není k dispozici pro symbol.  
  
## <a name="remarks"></a>Poznámky  
 `undecorateOptions` Může být kombinací následující příznaky.  
  
> [!NOTE]
>  Příznak názvy nejsou definovány v sadě DIA SDK, takže je třeba buď přidejte deklarace kódu, nebo použijte nezpracované hodnoty.  
  
|Příznak|Hodnota|Popis|  
|----------|-----------|-----------------|  
|UNDNAME_COMPLETE|0x0000|Povoluje úplné undecoration.|  
|UNDNAME_NO_LEADING_UNDERSCORES|0x0001|Odebere úvodní podtržítka od společnosti Microsoft rozšířené klíčová slova.|  
|UNDNAME_NO_MS_KEYWORDS|0x0002|Zakáže rozšíření Microsoft rozšířené klíčová slova.|  
|UNDNAME_NO_FUNCTION_RETURNS|0x0004|Zakáže rozšíření návratový typ pro primární deklarace.|  
|UNDNAME_NO_ALLOCATION_MODEL|0x0008|Zakáže rozšíření modelu deklarace.|  
|UNDNAME_NO_ALLOCATION_LANGUAGE|0x0010|Zakáže rozšíření specifikátor jazyk deklarace.|  
|UNDNAME_RESERVED1|0x0020|VYHRAZENA.|  
|UNDNAME_RESERVED2|0x0040|VYHRAZENA.|  
|UNDNAME_NO_THISTYPE|0x0060|Zakáže všechny modifikátory na `this` typu.|  
|UNDNAME_NO_ACCESS_SPECIFIERS|0x0080|Zakáže rozšíření přístup ke specifikátorům pro členy.|  
|UNDNAME_NO_THROW_SIGNATURES|0x0100|Zakáže rozšíření "throw-podpisů" pro funkce a ukazatelé na funkce.|  
|UNDNAME_NO_MEMBER_TYPE|hodnotu 0x0200|Zakáže rozšíření `static` nebo `virtual` členy.|  
|UNDNAME_NO_RETURN_UDT_MODEL|0x0400|Zakáže rozšíření Microsoft modelu pro UDT vrátí.|  
|UNDNAME_32_BIT_DECODE|0x0800|Dekorované názvy 32-bit undecorates.|  
|UNDNAME_NAME_ONLY|0x1000|Získá název pro primární deklaraci; Vrátí právě [oboru::] název.  Rozšíří parametry šablony.|  
|UNDNAME_TYPE_ONLY|0x2000|Vstup je právě typ kódování; Vytvoří abstraktní deklarátor.|  
|UNDNAME_HAVE_PARAMETERS|0x4000|Parametry skutečné šablony jsou k dispozici.|  
|UNDNAME_NO_ECSU|0x8000|Potlačí výčtu nebo třída nebo struktura/union.|  
|UNDNAME_NO_IDENT_CHAR_CHECK|0x10000|Potlačí kontrolu platný identifikátor – znaky.|  
|UNDNAME_NO_PTR64|0x20000|Nezahrnuje ptr64 ve výstupu.|  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)