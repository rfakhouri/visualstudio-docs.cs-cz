---
title: Připojovací řetězec obsahuje přihlašovací údaje s hesly v nešifrovaném textu a není používá integrované zabezpečení
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 501d85af-92e0-4471-b280-8a59c0688575
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: bf8a8fc3bb024c1eb8ee7baf91856a54dcb9d21f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="the-connection-string-contains-credentials-with-a-clear-text-password-and-is-not-using-integrated-security"></a>Připojovací řetězec obsahuje přihlašovací údaje s hesly v nešifrovaném textu a není používá integrované zabezpečení

Chcete uložit připojovací řetězec do aktuálního souboru DBML a konfigurační soubory aplikace s Tento citlivé informace?  Kliknutím na tlačítko Ne uložit připojovací řetězec bez citlivé informace.

Při práci s datovými připojeními, které obsahují citlivé informace (hesla, které jsou zahrnuty v připojovacím řetězci), budete mít připojovací řetězec uložit do souboru DBML projekt a konfigurační soubor aplikace bez ohledu citlivé informace.

> [!WARNING]
> Explicitní nastavení **připojení** vlastnosti **nastavení aplikace** vlastnost **False** přidá heslo do souboru DBML.

## <a name="to-save-the-connection-string-with-the-sensitive-information-in-the-projects-application-settings"></a>Připojovací řetězec uložit citlivé údaje v nastavení projektu aplikace

- Klikněte na tlačítko **Ano**.

   Připojovací řetězec je uloženo jako nastavení aplikace. Připojovací řetězec obsahuje důvěrné informace ve formátu prostého textu. Souboru DBML neobsahuje citlivé informace.

## <a name="to-save-the-connection-string-without-the-sensitive-information-in-the-projects-application-settings"></a>Uložit připojovací řetězec bez citlivých informací v aplikaci nastavení projektu

- Klikněte na tlačítko **ne**.

   Připojovací řetězec je uloženo jako nastavení aplikace, ale heslo není součástí.

## <a name="see-also"></a>Viz také

- [Zprávy Návrháře relací objektů](../data-tools/o-r-designer-messages.md)
- [Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)