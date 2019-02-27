---
title: Synchronně automaticky načtený rozšíření
ms.date: 02/16/2019
ms.topic: conceptual
ms.assetid: 822e3cf8-f723-4ff1-8467-e0fb42358a1f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 960fd54564bc25a8338461c30cd8a893e277b5a5
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/26/2019
ms.locfileid: "56844608"
---
# <a name="synchronously-autoloaded-extensions"></a>Synchronně automaticky načtený rozšíření

Rozšíření automaticky načtený synchronně mít negativní dopad na výkon sady Visual Studio a místo toho použít asynchronní autoload mají být převedeny. Od verze Visual Studio. 2019 ve verzi Preview 2, uživatelé budou upozorněni rozšíření se synchronně automaticky načtený. Rozšíření se načtou a fungují normálně.

![upozornění na kompatibilitu rozšíření](media/extension-compatibility-warning.png)

1. Uživatelé mohou klepnutím na **Další** zobrazíte na tuto stránku informace.

3. Uživatelé mohou klepnutím na **Správa výkonu** otevřít [dialogové okno Správce výkonu](#performance-manager-dialog) , která zobrazuje problémy s výkonem pomocí rozšíření a okna nástrojů.

3. Uživatelé mohou klepnutím na **tuto zprávu už nezobrazovat** chcete oznámení zavřít. Pokud vyberete tuto možnost, nebudou moct všechny budoucí oznámení z synchronně automaticky načtený rozšíření. Uživatelé budou dostávat oznámení o jiných funkcích sady Visual Studio.

### <a name="performance-manager-dialog"></a>Dialogové okno Správce výkonu

  ![Dialogové okno Správce výkonu](media/performance-manager.png)

Všechna rozšíření, která synchronně načíst všechny balíčky v jakékoli uživatelské relace se zobrazí v **API nepoužívané** kartu.

* Uživatelé mohou klepnutím na **Další informace o tomto problému** získáte další informace o rozhraních API nepoužívané.
* Můžou uživatelé kontaktovat svého dodavatele rozšíření pro průběh migrace.

Autoři rozšíření najdete pokyny k migraci balíčků do asynchronní autoload na [migrovat AsyncPackage](https://github.com/Microsoft/VSSDK-Extensibility-Samples/tree/master/AsyncPackageMigration).
