---
title: "Specifické pro Visual Basic IntelliSense | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IntelliSense [Visual Basic]
- IntelliSense [Visual Studio], Visual Basic
ms.assetid: 4dec8753-05e5-4f74-b304-5f8c4ed8723b
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f140a0eaf5d464ec4ead377d86257a8627fd6da4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="visual-basic-specific-intellisense"></a>Specifické pro jazyk Visual Basic IntelliSense
Editor kódu jazyka Visual Basic zdroj nabízí následující funkce IntelliSense:  
  
-   Syntaxe tipy  
  
     Syntaxe tipy zobrazení syntaxe příkazu, který zadáte. To je užitečné pro příkazy, jako například [Declare](/dotnet/visual-basic/language-reference/statements/declare-statement).  
  
## <a name="automatic-completion"></a>Automatické dokončování  
  
-   Dokončení na různých klíčová slova  
  
     Pokud zadáte například `goto` a místa, IntelliSense zobrazí seznam definovaných popisky v rozevírací nabídce. Zahrnout další podporované klíčová slova `Exit`, `Implements`, `Option`, a `Declare`.  
  
-   Dokončení na `Enum` a`Boolean`  
  
     Pokud příkaz bude odkaz na člena výčtu, IntelliSense zobrazí seznam členů `Enum`. V případě bude příkaz odkazujete `Boolean`, IntelliSense zobrazí rozevírací nabídky hodnotu true na false.  
  
 Dokončení může být vypnuto ve výchozím nastavení pomocí zrušením výběru **automatický seznam členů** z **Obecné** stránka vlastností v **jazyka Visual Basic** složky.  
  
 Dokončení můžete vyvolat ručně vyvoláním vypsat členy, dokončení slovo nebo ALT + Šipka vpravo. Další informace najdete v tématu [pomocí IntelliSense](../ide/using-intellisense.md).  
  
## <a name="intellisense-in-zone"></a>IntelliSense v zóně  
 IntelliSense v zóně pomáhá jazyka Visual Basic vývojáře, kteří potřebují nasazovat aplikace pomocí [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] a jsou omezená na nastavení částečné důvěryhodnosti. Tato funkce:  
  
-   Umožní vám vybrat oprávnění, která bude aplikace spuštěna s.  
  
-   Rozhraní API pro zobrazení v zvolený zónu jako dostupné v seznamu členů a zobrazit rozhraní API, které vyžadují další oprávnění jako nedostupné.  
  
 Další informace najdete v tématu [zabezpečení přístupu kódu pro aplikace ClickOnce](../deployment/code-access-security-for-clickonce-applications.md).  
  
## <a name="see-also"></a>Viz také  
 [Používání atributu IntelliSense](../ide/using-intellisense.md)