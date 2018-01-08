---
title: "Připojovací řetězec obsahuje přihlašovací údaje s hesly v nešifrovaném textu a není používá integrované zabezpečení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 501d85af-92e0-4471-b280-8a59c0688575
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 1ecca5a69893c92edbeb996606f94cac71e4a3c1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="the-connection-string-contains-credentials-with-a-clear-text-password-and-is-not-using-integrated-security"></a>Připojovací řetězec obsahuje přihlašovací údaje s hesly v nešifrovaném textu a není používá integrované zabezpečení
Chcete uložit připojovací řetězec do aktuálního souboru DBML a konfigurační soubory aplikace s Tento citlivé informace?  Kliknutím na tlačítko Ne uložit připojovací řetězec bez citlivé informace.  
  
 Při práci s datovými připojeními, které obsahují citlivé informace (hesla, které jsou zahrnuty v připojovacím řetězci), budete mít připojovací řetězec uložit do souboru DBML projekt a konfigurační soubor aplikace bez ohledu citlivé informace.  
  
> [!WARNING]
>  Explicitní nastavení **připojení** vlastnosti **nastavení aplikace** vlastnost **False** přidá heslo do souboru DBML.  
  
### <a name="to-save-the-connection-string-with-the-sensitive-information-in-the-projects-application-settings"></a>Připojovací řetězec uložit citlivé údaje v nastavení projektu aplikace  
  
-   Klikněte na tlačítko **Ano**.  
  
     Připojovací řetězec je uloženo jako nastavení aplikace. Připojovací řetězec obsahuje důvěrné informace ve formátu prostého textu. Souboru DBML neobsahuje citlivé informace.  
  
### <a name="to-save-the-connection-string-without-the-sensitive-information-in-the-projects-application-settings"></a>Uložit připojovací řetězec bez citlivých informací v aplikaci nastavení projektu  
  
-   Klikněte na tlačítko **ne**.  
  
     Připojovací řetězec je uloženo jako nastavení aplikace, ale heslo není součástí.  
  
## <a name="see-also"></a>Viz také
[Zprávy Návrháře relací objektů](../data-tools/o-r-designer-messages.md)  
[Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)