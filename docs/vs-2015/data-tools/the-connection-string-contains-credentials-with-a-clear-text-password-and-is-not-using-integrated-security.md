---
title: Připojovací řetězec obsahuje pověření s heslem prostý text a nevyužívá integrované zabezpečení | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 501d85af-92e0-4471-b280-8a59c0688575
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6d1be15ffdc204512c3034662b6ca24955869f5c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666763"
---
# <a name="the-connection-string-contains-credentials-with-a-clear-text-password-and-is-not-using-integrated-security"></a>Připojovací řetězec obsahuje přihlašovací údaje s heslem uloženým jako nešifrovaný text a nevyužívá integrované zabezpečení.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [připojovací řetězec obsahuje pověření s heslem prostý text a nevyužívá integrované zabezpečení](https://docs.microsoft.com/visualstudio/data-tools/the-connection-string-contains-credentials-with-a-clear-text-password-and-is-not-using-integrated-security).  
  
  
Chcete uložit připojovací řetězec do aktuálního souboru DBML a konfiguračních souborů aplikace s těmito citlivými informacemi?  Klikněte na tlačítko Ne a uložit připojovací řetězec bez citlivých informací.  
  
 Při práci s datová připojení, které obsahují citlivé informace (hesla, které jsou zahrnuty v připojovacím řetězci), budete mít možnost uložení připojovacího řetězce do souboru DBML a konfigurační soubor aplikace s nebo bez něj projektu citlivé informace.  
  
> [!WARNING]
>  Explicitním nastavením **připojení** vlastnosti **nastavení aplikace** vlastnost **False** přidá heslo k souboru DBML.  
  
### <a name="to-save-the-connection-string-with-the-sensitive-information-in-the-projects-application-settings"></a>Chcete-li uložit připojovací řetězec s citlivými informacemi v nastavení projektu aplikace  
  
-   Klikněte na tlačítko **Ano**.  
  
     Připojovací řetězec se ukládá jako nastavení aplikace. Připojovací řetězec obsahuje citlivé informace ve formátu prostého textu. Souboru DBML neobsahuje citlivé informace.  
  
### <a name="to-save-the-connection-string-without-the-sensitive-information-in-the-projects-application-settings"></a>Chcete-li uložit připojovací řetězec bez citlivých informací v aplikaci nastavení projektu  
  
-   Klikněte na tlačítko **ne**.  
  
     Připojovací řetězec se ukládá jako nastavení aplikace, ale heslo není zahrnutý.  
  
## <a name="see-also"></a>Viz také  
 [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)

