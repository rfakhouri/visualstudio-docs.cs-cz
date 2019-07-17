---
title: Aktualizace sady Visual Studio v servisním směrném plánu
description: Zjistěte, jak aktualizace sady Visual Studio při zachování směrný plán údržby.
ms.date: 05/22/2019
ms.custom: seodec18
ms.topic: conceptual
ms.assetid: ''
author: doughall
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: bf167c46e9b7dd9317278c7ce388977c4cc9428a
ms.sourcegitcommit: f369ff7e84b0216f01570a486c7be80ca6d0e61a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/16/2019
ms.locfileid: "68250332"
---
# <a name="update-visual-studio-while-on-a-servicing-baseline"></a>Aktualizace sady Visual Studio v servisním směrném plánu

Visual Studio 2019 bude mít časté aktualizace během její [životního cyklu produktu](/visualstudio/productinfo/release-rhythm#release-channel-updates). Aktualizace bude obsahovat aktualizace vedlejší verze (např. z 16.0 k 16.1), které můžou přidat nové funkce a součásti a servisní aktualizace (např. z 16.0.4 k 16.0.5), které obsahují pouze cílová opravy pro kritické problémy.

Organizace mohou správci uchovat své klienty v směrném plánu údržby. Směrný plán údržby se podporuje s aktualizace pro rok po vydání další údržby směrného plánu údržby.

Možnost údržby směrný plán poskytuje vývojářům a správcům větší flexibilitu, abyste mohli přejít na nové funkce, opravy chyb nebo komponenty, které jsou součástí nový dílčí aktualizace. První směrného plánu údržby je 16.0.x. Další informace najdete v tématu [možnosti podpory pro organizace a zákazníky se smlouvou professional](https://docs.microsoft.com/visualstudio/releases/2019/servicing#support-options-for-enterprise-and-professional-customers).

## <a name="how-to-get-onto-a-servicing-baseline"></a>Jak získat na směrný plán údržby

Pokud chcete začít používat směrný plán údržby, stáhněte si zaváděcí nástroj – verze sady Visual Studio Instalační program z [My.VisualStudio.com](https://my.visualstudio.com/Downloads?q=visual%20studio%202019%20version%2016.0). Bootstrapperů mají odkazy na konfigurace produktu, úlohy a komponenty pro tuto konkrétní verzi.

> [!NOTE]
> Buďte opatrní rozlišovat mezi zaváděcí nástroj – verze a standardní bootstrapperů. Standardní bootstrapperů umožňují použít nejnovější verzi sady Visual Studio, která je k dispozici. Standardní boostrappers obsahovat číslo v názvu souboru (například vs_enterprise__123456789-123456789.exe) Pokud jste stáhli z My.VisualStudio.com.

Během instalace musíte nakonfigurovat správcům jejich klientům zabránit klientům v aktualizaci na nejnovější verzi. Klienty můžete nakonfigurovat různými způsoby:
- [Změnit `channelUri` nastavení v konfiguračním souboru odezvy](update-servicing-baseline.md#install-a-servicing-baseline-on-a-network) použít manifest kanálu v rozložení nebo místní složky.
- [Upravit parametr channelUri prostřednictvím spuštění příkazového řádku](update-servicing-baseline.md#install-a-servicing-baseline-via-the-internet) neexistující soubor.
- [Nastavení zásad v klientském systému zakázat aktualizace](update-servicing-baseline.md#use-policy-settings-to-disable-clients-from-updating), čímž zabráníte klientům automatických aktualizací.

### <a name="install-a-servicing-baseline-on-a-network"></a>Instalace v síti směrný plán údržby

Správci, kteří používají instalace rozložení sítě by měl změnit `channelUri` hodnotu *response.json* souboru v rozložení chcete použít *channelmanifest.json* soubor, který je ve stejné složce. Kroky pro zajištění, naleznete v tématu [řízení aktualizací nasazení sady Visual Studio založené na síti](controlling-updates-to-visual-studio-deployments.md). Změna `channelUri` hodnota umožňuje klientům vyhledat aktualizace v umístění rozložení.

### <a name="install-a-servicing-baseline-via-the-internet"></a>Nainstalujte směrný plán údržby přes internet

Pro instalaci založené na Internetu, přidejte `--channelUri` kanálu neexistuje manifest pro příkazový řádek použitý ke spuštění instalace. Visual Studio zakáže pomocí nejnovější dostupné verze pro aktualizaci. Tady je příklad:

```cmd
vs_enterprise.exe --channelUri c:\doesnotexist.chman
```

### <a name="use-policy-settings-to-disable-clients-from-updating"></a>Použít nastavení zásad zakážete klientů z aktualizace

Další možností k řízení aktualizací na klientovi je [vypnout oznámení o aktualizacích](controlling-updates-to-visual-studio-deployments.md). Tuto možnost použijte, pokud parametr channelUri hodnota nebyla změněna na instalaci. Zakáže příjem odkazy na nejnovější dostupné verzi klienta. Zaváděcí nástroj-version je stále nutné aktualizovat na konkrétní verzi na straně klienta.

## <a name="how-to-stay-on-a-servicing-baseline"></a>Jak si udržet na směrný plán údržby

Pokud je k dispozici aktualizace pro směrný plán údržby, soubory bootstrapperu-version jsou k dispozici pro servisní aktualizace na [My.VisualStudio.com](https://my.visualstudio.com/Downloads?q=visual%20studio%202019%20version%2016.0).

Pro instalaci Správci nasazení prostřednictvím sítě rozložení správce chtít aktualizovat [umístění rozložení](update-a-network-installation-of-visual-studio.md). Klienti, kteří nainstalovány z umístění se zobrazí oznámení o aktualizacích. Pokud aktualizace musí být nasazený na klienty, postupujte podle [tyto pokyny](update-a-network-installation-of-visual-studio.md#how-to-deploy-an-update-to-client-machines). Při úpravě "response.json" pro aktualizaci, bez přidání dalších úloh, komponenty nebo jazyky. Správa těchto nastavení je nutné provést jako "upravit" nasazení po aktualizaci produktu.

Při instalaci internetových spustit nový zavaděč opravenou verzi s `--channelUri` parametr odkazuje na neexistující kanál manifest na straně klienta. Pokud se aktualizace nasadí v tichém nebo pasivním režimu, použijte dva různé příkazy:

1. Aktualizace instalačního programu sady Visual Studio:

    ```cmd
    vs_enterprise.exe --quiet --update
    ```

2. Aktualizujte vlastní aplikace Visual Studio:

    ```cmd
    vs_enterprise.exe update --installPath "C:\Program Files (x86)\Microsoft Visual Studio\2019\Enterprise" --quiet --wait --norestart --channelUri c:\doesnotexist.chman
    ```

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

* [Instalace sady Visual Studio](install-visual-studio.md)
* [Příručka pro správce aplikace Visual Studio](visual-studio-administrator-guide.md)
* [Instalace sady Visual Studio s použitím parametrů příkazového řádku](use-command-line-parameters-to-install-visual-studio.md)
* [Nástroje pro zjišťování a správu instancí sady Visual Studio](tools-for-managing-visual-studio-instances.md)
* [Definování nastavení v souboru odpovědí.](automated-installation-with-response-file.md)
* [Řízení aktualizací nasazení sady Visual Studio založené na síti](controlling-updates-to-visual-studio-deployments.md)
* [Životního cyklu produktu Visual Studio a údržba](/visualstudio/releases/2019/servicing/)
