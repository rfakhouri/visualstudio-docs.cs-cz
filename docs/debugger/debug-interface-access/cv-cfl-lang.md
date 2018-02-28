---
title: CV_CFL_LANG | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CV_CFL_LANG enumeration
ms.assetid: 4e8e0613-ad02-4de9-9f46-e4753c5b0251
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 12dfcf493432116fcba36d55d1a85b977e9058b0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="cvcfllang"></a>CV_CFL_LANG
Určuje jazyk zdrojového kódu aplikace nebo propojené modulu.  
  
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
 CV_CFL_C  
 Jazyk aplikace je C.  
  
 CV_CFL_CXX  
 Jazyk aplikace je C++.  
  
 CV_CFL_FORTRAN  
 Jazyk aplikace je FORTRAN.  
  
 CV_CFL_MASM  
 Jazyk aplikace je programu Microsoft Macro Assembler.  
  
 CV_CFL_PASCAL  
 Jazyk aplikace je Pascal.  
  
 CV_CFL_BASIC  
 Jazyk aplikace je BASIC.  
  
 CV_CFL_COBOL  
 Jazyk aplikace je COBOL.  
  
 CV_CFL_LINK  
 Aplikace je modul generované linkeru.  
  
 CV_CFL_CVTRES  
 Aplikace je modul prostředků převést pomocí nástroje CVTRES.  
  
 CV_CFL_CVTPGD  
 Aplikace je modul POGO optimalizované generovaný nástrojem CVTPGD.  
  
 CV_CFL_CSHARP  
 Jazyk aplikace je C#.  
  
 CV_CFL_VB  
 Jazyk aplikace je jazyka Visual Basic.  
  
 CV_CFL_ILASM  
 Jazyk aplikace je převodní jazyk sestavení (tedy sestavení Common Language Runtime (CLR)).  
  
 CV_CFL_JAVA  
 Jazyk aplikace je Java.  
  
 CV_CFL_JSCRIPT  
 Jazyk aplikace je Jscript.  
  
 CV_CFL_MSIL  
 Jazyk aplikace je neznámý Microsoft zprostředkující jazyk (MSIL), může být způsobeno tím, pomocí [/ltgc (vytváření kódu v době propojování)](/cpp/build/reference/ltcg-link-time-code-generation) přepínače.  
  
 CV_CFL_HLSL  
 Aplikace jazyk je jazyk shaderu vysoké úrovně.  
  
## <a name="remarks"></a>Poznámky  
 Hodnoty v tento výčet jsou vráceny prostřednictvím volání [idiasymbol::get_language –](../../debugger/debug-interface-access/idiasymbol-get-language.md) metoda.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: cvconst.h  
  
## <a name="see-also"></a>Viz také  
 [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_language](../../debugger/debug-interface-access/idiasymbol-get-language.md)