---
title: EVALFLAGS90 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- EVALFLAGS90 enumeration
ms.assetid: 64fb0139-8b04-4726-b52c-db2e04d65498
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 80f281e65d4dd7b2df24233552bdc46d4b29bebe
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="evalflags90"></a>EVALFLAGS90
Vytvoří výčet platné hodnoty pro příznaky, které řídí vyhodnocení výrazu. Tento výčet rozšiřuje [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_EVALFLAGS90  
{  
   // VS 8.0 values  
   EVAL90_RETURNVALUE                 = 0x0002,  
   EVAL90_NOSIDEEFFECTS               = 0x0004,  
   EVAL90_ALLOWBPS                    = 0x0008,  
   EVAL90_ALLOWERRORREPORT            = 0x0010,  
   EVAL90_FUNCTION_AS_ADDRESS         = 0x0040,  
   EVAL90_NOFUNCEVAL                  = 0x0080,  
   EVAL90_NOEVENTS                    = 0x1000,  
   EVAL90_DESIGN_TIME_EXPR_EVAL       = 0x2000,  
   EVAL90_ALLOW_IMPLICIT_VARS         = 0x4000,  
  
   // Values added in VS 9.0  
   EVAL90_FORCE_EVALUATION_NOW        = 0x8000  
};  
typedef DWORD EVALFLAGS90;  
```  
  
```csharp  
public enum enum_EVALFLAGS90  
{  
   // VS 8.0 values  
   EVAL90_RETURNVALUE                 = 0x0002,  
   EVAL90_NOSIDEEFFECTS               = 0x0004,  
   EVAL90_ALLOWBPS                    = 0x0008,  
   EVAL90_ALLOWERRORREPORT            = 0x0010,  
   EVAL90_FUNCTION_AS_ADDRESS         = 0x0040,  
   EVAL90_NOFUNCEVAL                  = 0x0080,  
   EVAL90_NOEVENTS                    = 0x1000,  
   EVAL90_DESIGN_TIME_EXPR_EVAL       = 0x2000,  
   EVAL90_ALLOW_IMPLICIT_VARS         = 0x4000,  
  
   // Values added in VS 9.0  
   EVAL90_FORCE_EVALUATION_NOW        = 0x8000  
};  
```  
  
#### <a name="parameters"></a>Parametry  
 EVAL90_RETURNVALUE  
 Určuje, že návratovou hodnotu, pokud existuje, vyhodnotí.  
  
 EVAL90_NOSIDEEFFECTS  
 Určuje, že nebyla povolen vedlejší účinky.  
  
 EVAL90_ALLOWBPS  
 Určuje zastavení zarážky.  
  
 EVAL90_ALLOWERRORREPORT  
 Určuje, že chybách k hostiteli mají být povolena. Používá se především pro vyhodnocení výrazu ve skriptu v aplikaci Internet Explorer.  
  
 EVAL90_FUNCTION_AS_ADDRESS  
 Vynutí funkce, který se má vyhodnotit jako adresy místo vyvolání funkce.  
  
 EVAL90_NOFUNCEVAL  
 Zabrání vyhodnocovaný funkce. Představte si třeba `int` tokenu ve výrazu `myExpression(int) + 10`. Tuto funkci lze správně vyhodnotit jako adresu, ale ne jako hodnotu.  
  
 EVAL90_NOEVENTS  
 Příznak, který označuje, že by se neměly posílat události, které nastaly během vyhodnocování výrazu, správce ladicí relace (SDM) nebo rozhraní IDE.  
  
 EVAL90_DESIGN_TIME_EXPR_EVAL  
 Umožňuje vyhodnocení výrazu při návrhu.  
  
 EVAL90_ALLOW_IMPLICIT_VARS  
 Umožňuje implicitní vytvoření proměnné.  
  
 EVAL90_FORCE_EVALUATION_NOW  
 Vynutí vyhodnocení proběhnout okamžitě. To je užitečné, když obsluhy požadavku, například na žádost uživatele.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Msdbg90.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)