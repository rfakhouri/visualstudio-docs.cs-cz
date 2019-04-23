---
title: 'Postupy: Použití úprav v režimu pozastavení pomocí operace upravit a pokračovat | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.variables.failededit
dev_langs:
- FSharp
- VB
- CSharp
- C++
- VB
helpviewer_keywords:
- Edit and Continue [Visual Basic], applying edits in break mode
- break mode, applying code changes
- Edit and Continue, applying edits in break mode
- editing, break mode
- coding, editing in break mode
- code, editing in break mode
ms.assetid: 1eef7498-6a1f-4fba-8146-510adc6375c9
caps.latest.revision: 33
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: e26b293a5ac7326ca8f82250ec3d0da9fe96371c
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60069923"
---
# <a name="how-to-apply-edits-in-break-mode-with-edit-and-continue"></a>Postupy: Použití úprav v režimu pozastavení pomocí operace upravit a pokračovat
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete upravit a pokračovat pro úpravy kódu v režimu pozastavení a potom pokračujte bez zastavení a restartování spuštění.  
  
 Upravit a pokračovat není k dispozici v následujících scénářích ladění:  
  
- Ladění ve smíšeném režimu (nativní a spravovaná).  
  
- Ladění SQL.  
  
- Ladění zotavení po havárii. Watson s výpisem paměti.  
  
- Úpravy kódu po neošetřené výjimky, když **vrátit zásobník volání v případě neošetřených výjimek** možnost není vybraná.  
  
- Ladění aplikace vložený modul runtime.  
  
- Ladění aplikace s **připojit k** místo spuštění aplikace s **Start** z **ladění** nabídky.  
  
- Ladění optimalizovaného kódu.  
  
- Ladění spravovaného kódu, pokud jsou cílem 64bitových aplikací. Pokud chcete k použití operace upravit a pokračovat, je nutné nastavit cíl na x86. (_Projektu_**vlastnosti**, **kompilaci** kartě **Advanced kompilátoru** nastavení.).  
  
- Ladění starou verzi kódu po nové verze se nepovedlo sestavit kvůli chybám sestavení.  
  
### <a name="to-edit-code-in-break-mode"></a>Pro úpravu kódu v režimu pozastavení  
  
1. Zadejte režimu pozastavení pomocí jedné z následujících akcí:  
  
    - Nastavte zarážku v kódu a pak zvolte **spustit ladění** z **ladění** nabídky a vyčkat, než aplikace k zarážce.  
  
         – nebo –  
  
    - Spustit ladění a pak vyberte **příkaz Pozastavit vše** z **ladění** nabídky.  
  
         – nebo –  
  
    - Když dojde k výjimce, zvolte **povolit úpravy** na**Pomocníka pro výjimky**.  
  
2. Proveďte změny požadované a právní kódu.  
  
     Další informace najdete v tématu [nepodporované úpravy v jazyce Visual Basic upravit a pokračovat](../debugger/unsupported-edits-in-visual-basic-edit-and-continue.md).  
  
    > [!NOTE]
    >  Při pokusu o aby kód změnit, která není povolena funkce upravit a pokračovat, úpravy bude podtržené podle fialovou vlnovkou a úloha se zobrazí v seznamu úkolů. Nebude moct pokračovat v provádění kódu není-li vrátit změnu neplatný kód.  
  
3. Na **ladění** nabídky, klikněte na tlačítko **pokračovat** pokračovat provádění.  
  
     S použité úpravy do projektu se teď spustí váš kód.  
  
## <a name="see-also"></a>Viz také  
 [Nepodporované úpravy v jazyce Visual Basic operaci upravit a pokračovat](../debugger/unsupported-edits-in-visual-basic-edit-and-continue.md)   
 [Upravit a pokračovat (Visual Basic)](../debugger/edit-and-continue-visual-basic.md)
