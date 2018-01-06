---
title: "Seznam úkolů, prostředí, dialogové okno Možnosti | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Environment.Task_List
- VS.ToolsOptionsPag.Environment.Task_List
- VS.ToolsOptionsPages.Environment.TaskList
- VS.Environment.Task List
helpviewer_keywords:
- Token List
- tokens
- icons, in Task List
- Task List, customizing environment
- Options dialog box, Task List environment
- exclamation points
- comments, comment tasks in Task List
- tokens, and the Task List
- Task List, comment tasks
ms.assetid: 88327e04-fa3e-48db-995b-ad89e0dc4ed2
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b6f8adfd3ce7d585cffe3c7506c4fdd56cad4a11
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="task-list-environment-options-dialog-box"></a>Seznam úloh, prostředí, dialogové okno Možnosti
Tato stránka Možnosti umožňuje přidat, odstranit a změňte komentář tokeny, které generují **seznam úkolů** připomenutí. K zobrazení těchto nastavení, vyberte **možnosti** z **nástroje** nabídky, rozbalte **prostředí** složku a zvolte **seznam úkolů**.  
  
## <a name="task-list-options"></a>Možnosti seznamu úkolů  
 Potvrdit odstranění úlohy  
 Při výběru, okno se zprávou se zobrazí pokaždé, když úlohu uživatele se odstraní z **seznam úkolů**, umožní vám potvrďte odstranění. Tato možnost je vybrána ve výchozím nastavení.  
  
> [!NOTE]
>  Pokud chcete odstranit komentář úloh, použijte odkaz k vyhledání komentář a potom odeberte z vašeho kódu.  
  
 Zobrazit pouze názvy souborů  
 Při výběru, **soubor** sloupec **seznam úkolů** zobrazí pouze názvy souborů k provádění úprav, není jejich úplné cesty.  
  
## <a name="tokens"></a>Tokeny  
 Když Vložit komentář do vašeho kódu, jejíž text začíná tokenu z **seznam tokenů**, **seznam úkolů** zobrazí komentář jako nová položka při každém otevření souboru pro úpravy. Kliknutí na toto tlačítko **seznam úkolů** položku přejít přímo na řádek komentáře v kódu. Další informace najdete v tématu [používání seznamu úkolů](../../ide/using-the-task-list.md).  
  
 seznam tokenů  
 Zobrazí seznam tokeny a umožňuje přidat nebo odebrat vlastní tokeny. Komentář tokeny jsou písmen v jazyce Visual C# a Visual C++, ale není v jazyce Visual Basic.  
  
> [!NOTE]
>  Pokud nezadáte požadovaný token přesně tak, jak se objevuje v **seznam tokenů**, úlohu komentář se nezobrazí v **seznam úkolů**.  
  
 Priorita  
 Nastaví prioritu úlohy, které využívají vybraný token. Úloh komentáře, které začínají tento token se automaticky přiřazují určené priority v **seznam úkolů**.  
  
 Název  
 Zadejte řetězec tokenu. Díky tomu **přidat** tlačítko. Na **přidat**, tento řetězec je součástí **seznam tokenů**, a komentáře, které začínají s tímto názvem se zobrazí v **seznam úkolů**.  
  
 Přidejte  
 Povolena, když zadáte nový **název**. Klikněte na tlačítko Přidat nový token řetězec pomocí zadaných hodnot **název** a **s prioritou** pole.  
  
 Odstranit  
 Klikněte na tlačítko Odstranit vybrané tokenu z **seznam tokenů**. Nelze odstranit výchozí token komentáře.  
  
 Změna  
 Klikněte na tlačítko Změnit token existující pomocí zadaných hodnot **název** a **s prioritou** pole.  
  
> [!NOTE]
>  Nelze přejmenovat nebo odstranit komentář výchozí token, ale můžete změnit její úroveň priority.  
  
## <a name="see-also"></a>Viz také  
 [Používání seznamu úloh](../../ide/using-the-task-list.md)   
 [Nastavení záložek v kódu](../../ide/setting-bookmarks-in-code.md)   
 [Prostředí, dialogové okno Možnosti](../../ide/reference/environment-options-dialog-box.md)