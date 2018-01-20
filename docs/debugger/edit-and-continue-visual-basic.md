---
title: "Upravit a pokračovat (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 10/11/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue, 64-bit
- Edit and Continue [Visual Basic]
- debugging [Visual Basic], Edit and Continue
- Visual Basic, Edit and Continue
- 64-bit Edit and Continue
ms.assetid: 7e90f34f-e699-45ab-a4c9-a4b527c498c8
caps.latest.revision: "40"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 82ec43b02895c2067b04f52f893184a82dd0f36b
ms.sourcegitcommit: 5d43e9590e2246084670b79269cc9d99124bb3df
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/19/2018
---
# <a name="edit-and-continue-visual-basic"></a>Upravit a pokračovat (Visual Basic)
Upravit a pokračovat, je funkce pro [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] ladění, který umožňuje změnit kódu, když je prováděna v režimu pozastavení. Po použití úprav kódu, můžete pokračovat v provádění kódu s novou úprav v místě a projevily.  
  
 Můžete použít upravit a pokračovat funkce vždy, když zadáte režim pozastavení. V režimu pozastavení, ukazatelem na instrukce, žlutý šipku v okně zdroj odkazuje na řádek obsahující příkazu spustitelný soubor do těla metody nebo vlastnosti, které se bude provést další.

 Upravit a pokračovat, podporuje většinu změn, které můžete chtít provést během ladicí relace, ale existují některé výjimky. Další informace najdete v tématu [podporované (C# a Visual Basic) změn kódu](../debugger/supported-code-changes-csharp.md).   
  
 Pokud provedete neoprávněným úpravy, změna je označené jako fialové vlnovkou a úlohy se zobrazí v seznamu úloh. Pokud chcete pokračovat v používání upravit a pokračovat, musíte vrátit neoprávněným upravit. Některé úpravy, neoprávněným může být povoleno, pokud se to udělá mimo upravit a pokračovat. Pokud chcete zachovat výsledky neoprávněným upravit, musíte ukončit ladění a restartujte aplikaci.  
  
 Upravit a pokračovat se podporuje v UWP aplikací pro Windows 10 a x86 a x64 aplikací, které se zaměřují rozhraní .NET Framework 4.6 desktop nebo novější verze (pouze plochy verze rozhraní .NET Framework je).

 > [!NOTE]
 > Nepodporované aplikace a platformy zahrnout ASP.NET 5, Silverlight 5 a Windows 8.1.
  
 Upravit a pokračovat není podporován při spuštění ladění pomocí **připojit k procesu**. Upravit a pokračovat není podporována pro optimalizovaného kódu nebo ve smíšeném spravovaná a nativní kód. Další informace najdete v tématu [podporované změny kódu (C# a Visual Basic](../debugger/supported-code-changes-csharp.md).
  
 Témata v této části obsahují další podrobnosti o tom, jak použít tuto funkci a jaké druhy změny nejsou povoleny.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Postupy: použití úprav v režimu pozastavení pomocí operace upravit a pokračovat](../debugger/how-to-apply-edits-in-break-mode-with-edit-and-continue.md)  
 Vysvětluje, jak se má použít kód úprav v režimu pozastavení.  
  
 [Podporované změny kódu (C# a Visual Basic](../debugger/supported-code-changes-csharp.md)   
 Popisuje, jaké typy úprav nelze provést v [!INCLUDE[vb_current_short](../debugger/includes/vb_current_short_md.md)] upravit a pokračovat.  
  
## <a name="related-sections"></a>Související oddíly  
 [Upravit a pokračovat](../debugger/edit-and-continue.md)  
 Obsahuje seznam témat, upravit a pokračovat.