---
title: Import a export konfigurací instalace
titleSuffix: ''
description: Další informace o použití funkce importu/exportu konfigurace sdílení .vsconfig souborů v sadě Visual Studio
ms.date: 05/17/2019
ms.topic: conceptual
f1_keywords:
- vs.about
helpviewer_keywords:
- import installation configuration
- export installation configuration
- install Visual Studio
- Visual Studio installer
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: 3644a0c04ebabab8744f6df21f9dd166665a21c4
ms.sourcegitcommit: 283f2dbce044a18e9f6ac6398f6fc78e074ec1ed
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/16/2019
ms.locfileid: "65805352"
---
# <a name="import-or-export-installation-configurations"></a>Import a export konfigurací instalace

Visual Studio můžete nakonfigurovat ve vaší organizaci pomocí instalace konfiguračních souborů. Uděláte to tak, jednoduše exportujte pracovního vytížení a komponenta informace do souboru .vsconfig pomocí instalačního programu sady Visual Studio. Můžete importovat konfiguraci do nových nebo stávajících zařízení a také sdílet s ostatními.

Tady je způsob.

::: moniker range="vs-2017"

> [!NOTE]
> Tato funkce je k dispozici pouze v sadě Visual Studio 2017 verze 15.9 nebo novější.

::: moniker-end

## <a name="export-a-configuration"></a>Exportovat konfiguraci

Můžete exportovat konfigurační soubor instalace z obou dříve nainstalovanou instanci sady Visual Studio nebo ten, který se právě instaluje.

1. Spusťte instalační program sady Visual Studio.

1. Na kartě produktu, zvolte **Další** tlačítko a pak vyberte **exportu konfigurace**.

   ![Exportovat konfiguraci z karty produktu v instalačním programu sady Visual Studio](../install/media/vs-2019/vs-installer-export-config.png)

1. Vyhledejte nebo zadejte umístění, kam chcete uložit soubor .vsconfig a klikněte na tlačítko **podrobnosti**.

   ![Exportovat konfiguraci z instalačního programu sady Visual Studio](../install/media/vs-2019/export-configuration-confirmation.png)

1. Ujistěte se, že máte úlohy a komponenty, které chcete a klikněte na tlačítko **exportovat**.

## <a name="import-a-configuration"></a>Importovat konfiguraci

Až budete připraveni importovat konfigurační soubor instalace, postupujte podle těchto kroků.

1. Spusťte instalační program sady Visual Studio.

1. Na kartě produktu, zvolte **Další** tlačítko a pak vyberte **importovat konfiguraci**.

1. Vyhledejte .vsconfig soubor, který chcete importovat a klikněte na tlačítko **podrobnosti**.

1. Ujistěte se, že máte úlohy a komponenty, které chcete a klikněte na tlačítko **Zavřít**.

::: moniker range="vs-2019"

## <a name="automatically-install-missing-components"></a>Automaticky nainstalovat chybějící součásti

**Novinka ve Visual Studio 2019**: Při uložení souboru .vsconfig do kořenového adresáře vašeho řešení a pak otevřete řešení sady Visual Studio automaticky zjišťuje komponenty, které chybí a zobrazí výzvu k instalaci.

![Průzkumník řešení navrhne další součásti](../install/media/vs-2019/solution-explorer-config-file.png)

Můžete také vygenerovat soubor .vsconfig přímo z Průzkumníka řešení.

1. Klikněte pravým tlačítkem na soubor řešení.

1. Zvolte **přidat** > **konfigurační soubor instalace**.

1. Potvrďte umístění, kam chcete uložit soubor .vsconfig a klikněte na tlačítko **podrobnosti**.

1. Ujistěte se, že máte úlohy a komponenty, které chcete a klikněte na tlačítko **exportovat**.

::: moniker-end

> [!NOTE]
> Další informace najdete v tématu [konfigurace sady Visual Studio napříč vaší organizací s .vsconfig](https://devblogs.microsoft.com/setup/configure-visual-studio-across-your-organization-with-vsconfig/) blogový příspěvek.

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

* [Vytvoření síťové instalace sady Visual Studio](create-a-network-installation-of-visual-studio.md)
* [Aktualizace na základě síťové instalace sady Visual Studio](update-a-network-installation-of-visual-studio.md)
* [Řízení aktualizací nasazení sady Visual Studio](controlling-updates-to-visual-studio-deployments.md)
* [Výchozí nastavení v případě podnikového nasazení](set-defaults-for-enterprise-deployments.md)
