---
title: Připojovací řetězec obsahuje přihlašovací údaje s heslem uloženým jako nešifrovaný text a nevyužívá integrované zabezpečení.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 501d85af-92e0-4471-b280-8a59c0688575
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: b270290c948807ff0f66d3d142312245475cd33c
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65460610"
---
# <a name="the-connection-string-contains-credentials-with-a-clear-text-password-and-is-not-using-integrated-security"></a>Připojovací řetězec obsahuje přihlašovací údaje s heslem uloženým jako nešifrovaný text a nevyužívá integrované zabezpečení.

Chcete uložit připojovací řetězec do aktuálního souboru DBML a konfiguračních souborů aplikace s těmito citlivými informacemi?  Klikněte na tlačítko **ne** uložit připojovací řetězec bez citlivých informací.

Při práci s datová připojení, které obsahují citlivé informace (hesla, které jsou zahrnuty v připojovacím řetězci), budete mít možnost uložení připojovacího řetězce do souboru DBML a konfigurační soubor aplikace s nebo bez něj projektu citlivé informace.

> [!WARNING]
> Explicitním nastavením **připojení** vlastnosti **nastavení aplikace** vlastnost **False** přidá heslo k souboru DBML.

## <a name="save-options"></a>Možnosti uložení

- Chcete-li uložit připojovací řetězec s citlivými informacemi, zvolte **Ano**.

   Připojovací řetězec se ukládá jako nastavení aplikace. Připojovací řetězec obsahuje citlivé informace ve formátu prostého textu. Souboru DBML neobsahuje citlivé informace.

- Chcete-li uložit připojovací řetězec bez citlivých informací, zvolte **ne**.

   Připojovací řetězec se ukládá jako nastavení aplikace, ale heslo není zahrnutý.

## <a name="see-also"></a>Viz také:

- [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)