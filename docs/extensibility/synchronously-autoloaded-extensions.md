---
title: Automaticky synchronně načítaná rozšíření
ms.date: 02/16/2019
ms.topic: conceptual
ms.assetid: 822e3cf8-f723-4ff1-8467-e0fb42358a1f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ad3831fb06d23f622f85a55f5efd0a5650ca5e47
ms.sourcegitcommit: 62149c96de0811415e99bb1e0194e76c320e1a1e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2019
ms.locfileid: "57007160"
---
# <a name="synchronously-autoloaded-extensions"></a>Automaticky synchronně načítaná rozšíření

Rozšíření automaticky načtený synchronně mít negativní dopad na výkon sady Visual Studio a místo toho použít asynchronní autoload mají být převedeny. Spouští se v sadě Visual Studio. 2019 ve verzi Preview 2, uživatelům se zobrazí oznámení rozšíření se synchronně automaticky načtený. Rozšíření se načtou a fungují normálně.

![upozornění na kompatibilitu rozšíření](media/extension-compatibility-warning.png)

Uživatelé můžou:

- Klikněte na **Další** zobrazíte na tuto stránku informace.

- Klikněte na **Správa výkonu** otevřít [dialogové okno Správce výkonu](#performance-manager-dialog) , která zobrazuje problémy s výkonem pomocí rozšíření a okna nástrojů.

- Klikněte na **tuto zprávu už nezobrazovat** chcete oznámení zavřít. Pokud vyberete tuto možnost, zabrání se také všechny budoucí oznámení z synchronně automaticky načtený rozšíření. Uživatelé budou dostávat oznámení o jiných funkcích sady Visual Studio.

### <a name="performance-manager-dialog"></a>Dialogové okno Správce výkonu

![Dialogové okno Správce výkonu](media/performance-manager.png)

Zobrazí všechna rozšíření, která synchronně načíst všechny balíčky v jakékoli uživatelské relace v **API nepoužívané** kartu.

* Uživatelé mohou klepnutím na **Další informace o tomto problému** získáte další informace o rozhraních API nepoužívané.
* Můžou uživatelé kontaktovat svého dodavatele rozšíření pro průběh migrace.

Autoři rozšíření najdete pokyny k migraci balíčků do asynchronní autoload na [migrovat AsyncPackage](https://github.com/Microsoft/VSSDK-Extensibility-Samples/tree/master/AsyncPackageMigration).
