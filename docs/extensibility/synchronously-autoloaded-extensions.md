---
title: Automaticky synchronně načítaná rozšíření
ms.date: 02/16/2019
ms.topic: conceptual
ms.assetid: 822e3cf8-f723-4ff1-8467-e0fb42358a1f
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8b18642269326c516c2af0baef57cb306f60ae6a
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66316716"
---
# <a name="synchronously-autoloaded-extensions"></a>Automaticky synchronně načítaná rozšíření

Rozšíření automaticky načtený synchronně mít negativní dopad na výkon sady Visual Studio a místo toho použít asynchronní autoload mají být převedeny. Spouští se v sadě Visual Studio. 2019 ve verzi Preview 2, uživatelům se zobrazí oznámení rozšíření se synchronně automaticky načtený. Rozšíření se načtou a fungují normálně.

![upozornění na kompatibilitu rozšíření](media/extension-compatibility-warning.png)

Uživatelé můžou:

- Klikněte na **Další** zobrazíte na tuto stránku informace.

- Klikněte na **Správa výkonu** otevřít [dialogové okno Správce výkonu](#performance-manager-dialog) , která zobrazuje problémy s výkonem pomocí rozšíření a okna nástrojů.

- Klikněte na **tuto zprávu už nezobrazovat** chcete oznámení zavřít. Pokud vyberete tuto možnost, zabrání se také všechny budoucí oznámení z synchronně automaticky načtený rozšíření. Uživatelé budou dostávat oznámení o jiných funkcích sady Visual Studio.

## <a name="performance-manager-dialog"></a>Dialogové okno Správce výkonu

![Dialogové okno Správce výkonu](media/performance-manager.png)

Zobrazí všechna rozšíření, která synchronně načíst všechny balíčky v jakékoli uživatelské relace v **API nepoužívané** kartu.

* Uživatelé mohou klepnutím na **Další informace o tomto problému** získáte další informace o rozhraních API nepoužívané.
* Můžou uživatelé kontaktovat svého dodavatele rozšíření pro průběh migrace.

Autoři rozšíření najdete pokyny k migraci balíčků do asynchronní autoload na [migrovat AsyncPackage](https://github.com/Microsoft/VSSDK-Extensibility-Samples/tree/master/AsyncPackageMigration).

## <a name="specify-synchronous-autoload-settings-using-group-policy"></a>Zadejte nastavení synchronní autoload pomocí zásad skupiny

Visual Studio. 2019 Update 1, spouští se ve výchozím nastavení, autoload synchronní bloky instalace sady Visual Studio. Když povolíte zásady skupiny, můžete nakonfigurovat sady Visual Studio umožňuje synchronní autoload v jednotlivých počítačích. Uděláte to tak, nastavte zásadu založenou na registru pro následující klíč:

**HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\VisualStudio\SynchronousAutoload**

Položka = **povoleno**

Hodnota = (DWORD)
* **0** nepovoluje synchronní autoload
* **1** smí synchronní autoload

Další informace o nastavení synchronní autoload ve Visual Studiu 2019 Update 1 najdete v článku [synchronní chování Autoload](https://aka.ms/AA52xzw) stránky.
