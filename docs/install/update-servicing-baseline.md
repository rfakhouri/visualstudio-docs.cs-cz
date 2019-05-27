---
title: Aktualizace sady Visual Studio na směrný plán údržby
titleSuffix: ''
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
ms.openlocfilehash: 8928feffed77f8bfbb3787bd9a20737b9c7b3f9e
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66213848"
---
# <a name="update-visual-studio-while-on-a-servicing-baseline"></a>Aktualizace sady Visual Studio na směrný plán údržby

Visual Studio 2019 bude mít časté aktualizace během její [životního cyklu produktu](/visualstudio/productinfo/release-rhythm.md#release-channel-updates). Patří oba vedlejší verze aktualizace (například: 16.0 k 16.1), které zahrnují nové funkce a součásti a opravné aktualizace (například: 16.0.4 k 16.0.5) obsahující pouze cílová opravy pro kritické problémy. 

Organizace mohou správci uchovat své klienty v údržby směrný plán, který je podporován aktualizace pro rok po vydání další údržby směrného plánu údržby. Díky tomu větší flexibilitu pro vývojáře a správce, abyste mohli přejít na nové funkce, opravy chyb nebo komponenty, které jsou součástí nový dílčí aktualizace. První směrného plánu údržby je 16.0.x. Zobrazit [možnosti podpory pro organizace a zákazníky se smlouvou professional](/visualstudio/releases/2019/servicing.md#support-options-for-enterprise-and-professional-customers) Další informace.

## <a name="how-to-get-onto-a-servicing-baseline"></a>Jak získat na směrný plán údržby

Chcete-li začít používat směrný plán údržby, stáhněte si zaváděcí nástroj opravenou verzi instalačního programu sady Visual Studio z [My.VisualStudio.com](https://my.visualstudio.com/Downloads?q=visual%20studio%202019%20version%2016.0). Tyto bootstrapperů mají odkazy na konfigurace produktu, úlohy a komponenty pro tuto konkrétní verzi. 

> [!NOTE]
> Buďte opatrní rozlišovat mezi zaváděcí nástroj opravenou verzi a normální bootstrapperů. Normální bootstrapperů umožňují použít nejnovější verzi sady Visual Studio, která je k dispozici. Číslo mají v názvu souboru (například: vs_enterprise__123456789 123456789.exe) v případě stažený z my.visualstudio.com.

Během instalace správcům pak stačí ke konfiguraci svých klientech a zabrání tak jejich aktualizace na nejnovější verzi. To můžete udělat [Změna nastavení parametr channelUri v konfiguračním souboru odezvy](update-servicing-baseline.md#install-a-servicing-baseline-on-a-network) použít manifest kanálu v rozložení nebo místní složky pomocí [úpravy parametr channelUri prostřednictvím příkazového řádku spuštění](update-servicing-baseline.md#install-a-servicing-baseline-via-the-internet)použít soubor neexistuje, nebo [nastavení zásad v klientském systému zakázat aktualizace](update-servicing-baseline.md#use-policy-settings-to-disable-clients-from-updating) chcete klientům zabránit automatických aktualizací. 

### <a name="install-a-servicing-baseline-on-a-network"></a>Instalace v síti směrný plán údržby

Pro správce pomocí síťový diagram nainstalovat, upravte hodnotu parametr channelUri v `response.json` v rozložení chcete použít channelmanifest.json, který je ve stejné složce. Zobrazit [řízení aktualizací nasazení sady Visual Studio založené na síti](controlling-updates-to-visual-studio-deployments.md) podrobné pokyny. Změna parametr channelUri umožňuje klientům vyhledat aktualizace v umístění rozložení. 

### <a name="install-a-servicing-baseline-via-the-internet"></a>Nainstalujte směrný plán údržby přes internet

Pokud je instalace k Internetu, přidejte `--channelUri` kanálu neexistuje manifest pro příkazový řádek použitý ke spuštění instalace. Visual Studio zakáže pomocí nejnovější dostupné verze pro aktualizaci. Tady je příklad:

  ```cmd
   vs_enterprise.exe --channelUri c:\doesnotexist.chman 
  ```

### <a name="use-policy-settings-to-disable-clients-from-updating"></a>Použít nastavení zásad zakážete klientů z aktualizace

Další možností k řízení aktualizací na klientovi je [vypnout oznámení o aktualizacích](controlling-updates-to-visual-studio-deployments.md). Tuto možnost použijte, pokud parametr channelUri hodnota nebyla změněna při instalaci. Zakáže příjem odkazy na nejnovější dostupné verzi klienta. Zaváděcí nástroj opravenou verzi je stále nutné aktualizovat na konkrétní verzi na straně klienta.

## <a name="how-to-stay-on-a-servicing-baseline"></a>Jak si udržet na směrný plán údržby

Když je aktualizace pro směrný plán údržby, soubory bootstrapperu opravenou verzi jsou k dispozici pro servisní aktualizace z [My.VisualStudio.com](https://my.visualstudio.com/Downloads?q=visual%20studio%202019%20version%2016.0). Ty je možné v několika situacích.

Pro instalaci Správci nasazení prostřednictvím sítě rozložení správce chtít aktualizovat [umístění rozložení](update-a-network-installation-of-visual-studio.md). Klienti, kteří nainstalovány z umístění se zobrazí oznámení o aktualizacích. Pokud aktualizace musí být nasazený na klienty, postupujte podle [tyto pokyny](update-a-network-installation-of-visual-studio.md#how-to-deploy-an-update-to-client-machines). Při úpravě "response.json" pro aktualizaci, bez přidání dalších úloh, komponenty nebo jazyky. Správa těchto nastavení je nutné provést jako "upravit" nasazení po aktualizaci produktu. 

Pokud je instalace k Internetu, spusťte nové opravenou verzi bootstrapperu s `--channelUri` parametr odkazuje na neexistující kanál manifest na straně klienta. Pokud se aktualizace nasadí v tichém nebo pasivním režimu, použijte dva různé příkazy:

1. Nejprve aktualizace instalačního programu sady Visual Studio: <br>```vs_enterprise.exe --quiet --update```
2. Potom aktualizujte vlastní aplikace Visual Studio: <br>```vs_enterprise.exe update --installPath "C:\Program Files (x86)\Microsoft Visual Studio\2019\Enterprise" --quiet --wait --norestart --channelUri c:\doesnotexist.chman```

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

* [Instalace sady Visual Studio](install-visual-studio.md)
* [Příručka pro správce aplikace Visual Studio](visual-studio-administrator-guide.md)
* [Instalace sady Visual Studio s použitím parametrů příkazového řádku](use-command-line-parameters-to-install-visual-studio.md)
* [Nástroje pro zjišťování a správu instancí sady Visual Studio](tools-for-managing-visual-studio-instances.md)
* [Definování nastavení v souboru odpovědí.](automated-installation-with-response-file.md)
* [Řízení aktualizací nasazení sady Visual Studio založené na síti](controlling-updates-to-visual-studio-deployments.md)
* [Životního cyklu produktu Visual Studio a údržba](/visualstudio/releases/2019/servicing/)
