---
title: Specifické pro jazyk Visual Basic IntelliSense | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- IntelliSense [Visual Basic]
- IntelliSense [Visual Studio], Visual Basic
ms.assetid: 4dec8753-05e5-4f74-b304-5f8c4ed8723b
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 629683131b93534350439867e41b97ca3bbf3b5a
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60106875"
---
# <a name="visual-basic-specific-intellisense"></a>Specifické pro jazyk Visual Basic IntelliSense
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Editor zdrojového kódu jazyka Visual Basic nabízí následující funkce IntelliSense:  
  
- Syntaxe tipy  
  
     Syntaxe tipy zobrazení syntaxe příkazu, který píšete. To je užitečné pro příkazy, jako [Declare](http://msdn.microsoft.com/library/d3f21fb0-b804-4c99-97ed-583b23894cf1).  
  
## <a name="automatic-completion"></a>Automatické dokončování  
  
- Dokončení různých klíčových slov  
  
   Pokud zadáte například `goto` a mezerou, technologie IntelliSense zobrazí seznam popisků definované v rozevírací nabídce. Zahrnout další podporované klíčová slova `Exit`, `Implements`, `Option`, a `Declare`.  
  
- Dokončení `Enum` a `Boolean`  
  
   Pokud příkaz bude odkazovat na člena výčtu, technologie IntelliSense zobrazí seznam členů `Enum`. Pokud příkaz bude odkazovat `Boolean`, technologie IntelliSense se zobrazí rozevírací nabídky true na false.  
  
  Dokončení může být ve výchozím nastavení vypnuta odznačením **automatický seznam členů** z **Obecné** stránku vlastností v **jazyka Visual Basic** složky.  
  
  Dokončení lze vyvolat ručně vyvoláním seznam členů, úplné slovo nebo ALT + Šipka vpravo. Další informace najdete v tématu [pomocí technologie IntelliSense](../ide/using-intellisense.md).  
  
## <a name="intellisense-in-zone"></a>IntelliSense in Zone  
 Technologie IntelliSense v zóně pomáhá vývojáře jazyka Visual Basic, kteří potřebují nasazovat aplikace prostřednictvím [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] a jsou omezeny na nastavení částečným vztahem důvěryhodnosti. Tuto funkci:  
  
- Umožní vám vybrat oprávnění, která bude aplikace spuštěna s.  
  
- Rozhraní API zobrazení ve vybrané jako dostupné v seznamu členů zóny a zobrazit rozhraní API, která vyžadují další oprávnění jako nedostupné.  
  
  Další informace najdete v tématu [Code Access Security for ClickOnce Applications](../deployment/code-access-security-for-clickonce-applications.md).  
  
## <a name="see-also"></a>Viz také  
 [Používání atributu IntelliSense](../ide/using-intellisense.md)
