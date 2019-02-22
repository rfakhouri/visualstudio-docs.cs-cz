---
title: CV_CFL_LANG | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CV_CFL_LANG enumeration
ms.assetid: 4e8e0613-ad02-4de9-9f46-e4753c5b0251
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1f02545f1c19b57e46af302fbc0b2abaa7445612
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56646340"
---
# <a name="cvcfllang"></a>CV_CFL_LANG
Určuje jazyk zdrojového kódu aplikace nebo propojeném modulu.

## <a name="syntax"></a>Syntaxe

```C++
typedef enum CV_CFL_LANG {
    CV_CFL_C       = 0x00,
    CV_CFL_CXX     = 0x01,
    CV_CFL_FORTRAN = 0x02,
    CV_CFL_MASM    = 0x03,
    CV_CFL_PASCAL  = 0x04,
    CV_CFL_BASIC   = 0x05,
    CV_CFL_COBOL   = 0x06,
    CV_CFL_LINK    = 0x07,
    CV_CFL_CVTRES  = 0x08,
    CV_CFL_CVTPGD  = 0x09,
    CV_CFL_CSHARP  = 0x0A,
    CV_CFL_VB      = 0x0B,
    CV_CFL_ILASM   = 0x0C,
    CV_CFL_JAVA    = 0x0D,
    CV_CFL_JSCRIPT = 0x0E,
    CV_CFL_MSIL    = 0x0F,
    CV_CFL_HLSL    = 0x10
} CV_CFL_LANG;
```

## <a name="elements"></a>Elementy
Je aplikace CV_CFL_C jazyka C.

Je aplikace CV_CFL_CXX jazyk C++.

Je jazyk CV_CFL_FORTRAN aplikace až po FORTRAN.

Microsoft Macro Assembler je jazyk CV_CFL_MASM aplikace.

Pascal je jazyk CV_CFL_PASCAL aplikace.

Jazyk CV_CFL_BASIC aplikace je BASIC.

Jazyk CV_CFL_COBOL aplikace je COBOL.

CV_CFL_LINK aplikace je modul vytvořeného v propojovacím programu.

Modul prostředků převést pomocí nástroje CVTRES je CV_CFL_CVTRES aplikace.

CV_CFL_CVTPGD aplikace je modul optimalizovaný POGO generovaný nástrojem CVTPGD.

Je jazyk aplikace CV_CFL_CSHARP C#.

Je CV_CFL_VB aplikace jazyka Visual Basic.

Jazyk CV_CFL_ILASM aplikace je sestavení převodní jazyk (to znamená, že sestavení Common Language Runtime (CLR)).

Je jazyk CV_CFL_JAVA aplikace Java.

Jazyk CV_CFL_JSCRIPT aplikace je Jscript.

Jazyk CV_CFL_MSIL aplikace je neznámý Microsoft Intermediate Language (MSIL), může být způsobeno použitím [parametru/LTCG (generování kódu při propojování odkaz)](/cpp/build/reference/ltcg-link-time-code-generation) přepnout.

Aplikace CV_CFL_HLSL jazyk je jazyk shaderu vysokou úroveň.

## <a name="remarks"></a>Poznámky
Hodnoty v tomto výčtu jsou vráceny prostřednictvím volání [idiasymbol::get_language –](../../debugger/debug-interface-access/idiasymbol-get-language.md) metody.

## <a name="requirements"></a>Požadavky
Záhlaví: cvconst.h

## <a name="see-also"></a>Viz také
- [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)
- [IDiaSymbol::get_language](../../debugger/debug-interface-access/idiasymbol-get-language.md)
