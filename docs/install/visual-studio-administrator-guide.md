---
title: Příručka správce sady Visual Studio
titleSuffix: ''
description: Další informace o tom, jak nasadit aplikaci Visual Studio v podnikovém prostředí.
ms.date: 05/22/2019
ms.custom: seodec18
ms.topic: conceptual
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
ms.assetid: 4af353f5-6cfd-4ebe-bcfb-f42306e451a0
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: 61b3a2dfae667bac7c3a6a62682cdbd5b1a5feb4
ms.sourcegitcommit: cd21b38eefdea2cdefb53e68e7a30b868e78dd6b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/22/2019
ms.locfileid: "66037488"
---
# <a name="visual-studio-administrator-guide"></a>Příručka správce sady Visual Studio

V podnikových prostředích správci systému obvykle nasazení instalace pro koncové uživatele ze sdílené síťové složce nebo s použitím softwaru pro správu systému. Jsme navrhli tak nastavení modul sady Visual Studio pro podporu nasazení v podnikovém prostředí tím, že správci systému umožňuje vytvořit umístění v síti nainstalovat, předem nakonfigurovat výchozí nastavení instalace, nasazení kódy product key během procesu instalace a Správa aktualizací produktu po úspěšné zavedení.

Tato příručka pro správce poskytuje pokyny založené na scénářích pro rozsáhlá nasazení v síťovém prostředí.

## <a name="before-you-begin"></a>Před zahájením

Před nasazením aplikace Visual Studio napříč vaší organizací, existuje několik rozhodnutí a na dokončení úloh:

::: moniker range="vs-2019"

* Ujistěte se, že každý cílový počítač splňuje [minimální požadavky na instalaci](/visualstudio/releases/2019/system-requirements/).

* Při rozhodování o potřebách údržby.

  Pokud vaše společnost potřebuje zůstat na funkci nastavit už ale stále chce dostávat pravidelné údržby aktualizace, naplánujte použití směrný plán údržby. Další informace najdete v tématu ***možnosti podpory pro zákazníky s Enterprise nebo Professional*** část [životního cyklu produktu Visual Studio a údržba](/visualstudio/releases/2019/servicing#support-options-for-enterprise-and-professional-customers) stránky.

  Pokud máte v plánu údržby aktualizace spolu s funkcí kumulativní aktualizace, můžete nejnovější součásti.

* Při rozhodování o aktualizace modelu.

  Pokud chcete jednotlivých klientských počítačů má být aktualizován Konkrétně rozhodnete, jestli chcete získat aktualizace z Internetu nebo ze sdílené složky místní pořádaného microsoftem. Pokud se rozhodnete použít místní sdílenou složku, rozhodněte, jestli jednotlivým uživatelům můžete aktualizovat své vlastní klienty nebo pokud chcete, aby správce programově aktualizovat klienty.

* Rozhodněte, která [úlohy a komponenty](workload-and-component-ids.md?view=vs-2019) vašim firemním potřebám.

* Rozhodněte, jestli se má použít [soubor odpovědí](automated-installation-with-response-file.md?view=vs-2019) (zjednodušuje správu podrobnosti v souboru skriptu).

* Rozhodněte, pokud chcete povolit zásady skupiny, a pokud chcete provést konfiguraci sady Visual Studio k zakázání zpětné vazby od zákazníků v jednotlivých počítačích.

::: moniker-end

::: moniker range="vs-2017"

* Ujistěte se, že každý cílový počítač splňuje [minimální požadavky na instalaci](/visualstudio/productinfo/vs2017-system-requirements-vs/).

* Při rozhodování o potřebách údržby.

  Pokud vaše společnost potřebuje zůstat na funkci nastavit už ale stále chce dostávat pravidelné údržby aktualizace, naplánujte použití směrný plán údržby. Další informace najdete v tématu ***podpora pro starší verze sady Visual Studio*** část [životního cyklu produktu Visual Studio a údržba](/visualstudio/releases/2019/servicing#support-for-older-versions-of-visual-studio) stránky.

  Pokud máte v plánu údržby aktualizace spolu s funkcí kumulativní aktualizace, můžete nejnovější součásti.

* Při rozhodování o aktualizace modelu.

  Pokud chcete jednotlivých klientských počítačů má být aktualizován Konkrétně rozhodnete, jestli chcete získat aktualizace z Internetu nebo ze sdílené složky místní pořádaného microsoftem. Pokud se rozhodnete použít místní sdílenou složku, rozhodněte, jestli jednotlivým uživatelům můžete aktualizovat své vlastní klienty nebo pokud chcete, aby správce programově aktualizovat klienty.

* Rozhodněte, která [úlohy a komponenty](workload-and-component-ids.md?view=vs-2017) vašim firemním potřebám.

* Rozhodněte, jestli se má použít [soubor odpovědí](automated-installation-with-response-file.md?view=vs-2017) (zjednodušuje správu podrobnosti v souboru skriptu).

* Rozhodněte, pokud chcete povolit zásady skupiny, a pokud chcete provést konfiguraci sady Visual Studio k zakázání zpětné vazby od zákazníků v jednotlivých počítačích.

::: moniker-end

::: moniker range="vs-2019"

## <a name="step-1---download-visual-studio-product-files"></a>Krok 1: Stáhněte si soubory produktu Visual Studio

* [Vyberte úlohy a komponenty](workload-and-component-ids.md?view=vs-2019) , kterou chcete nainstalovat.

* [Vytvoření sdílené síťové složky pro soubory produktu Visual Studio](create-a-network-installation-of-visual-studio.md?view=vs-2019).

## <a name="step-2---build-an-installation-script"></a>Krok 2: vytvoření instalačního skriptu

* Vytváření instalačního skriptu, který používá [parametry příkazového řádku](use-command-line-parameters-to-install-visual-studio.md?view=vs-2019) řízení instalace.

  >[!NOTE]
  > Můžete zjednodušit pomocí skriptů [soubor odpovědí](automated-installation-with-response-file.md?view=vs-2019). Ujistěte se, že chcete vytvořit soubor odpovědí, který obsahuje výchozí možností instalace.

* (Volitelné) [Použít volume license product key](automatically-apply-product-keys-when-deploying-visual-studio.md?view=vs-2019) jako součást instalace skript tak, aby uživatelé nemuseli aktivovat software samostatně.

* (Volitelné) Aktualizace rozložení sítě, které [řídit, kdy a kde z produktu doručování aktualizací na vaše koncové uživatele](controlling-updates-to-visual-studio-deployments.md?view=vs-2019).

* (Volitelné) Nastavení zásad registru, které ovlivní také nasazení sady Visual Studio, jako je například, kde jsou nainstalovány některé balíčky sdílené s jinými verzemi nebo instance, [kde balíčky v mezipaměti](set-defaults-for-enterprise-deployments.md?view=vs-2019) nebo [Určuje, zda jsou balíčky v mezipaměti](disable-or-move-the-package-cache.md?view=vs-2019).

* (Volitelné) Nastavení zásad skupiny. Můžete také [konfigurace sady Visual Studio k zakázání zpětné vazby od zákazníků](../ide/visual-studio-experience-improvement-program.md) v jednotlivých počítačích.

## <a name="step-3---deploy"></a>Krok 3 – nasazení

* Zvolených technologií nasazení použijte ke spuštění skriptu na vaše cílové vývojářské pracovní stanice.

## <a name="step-4---deploy-updates"></a>Krok 4: nasazení aktualizací

* [Aktualizujte vaše umístění v síti s nejnovějšími aktualizacemi](update-a-network-installation-of-visual-studio.md?view=vs-2019) do sady Visual Studio spuštěním příkazu, který jste použili v kroku 1 v pravidelných intervalech a přidejte aktualizované součásti.

  Visual Studio můžete aktualizovat pomocí aktualizační skript. Chcete-li tak učinit, použijte [ `update` ](use-command-line-parameters-to-install-visual-studio.md?view=vs-2019) parametr příkazového řádku.

## <a name="step-5---optional-use-visual-studio-tools"></a>Krok 5: (volitelné) pomocí aplikace Visual Studio tools

Máme několik nástrojů, které vám pomůžou [zjišťovat a spravovat nainstalované instance sady Visual Studio](tools-for-managing-visual-studio-instances.md?view=vs-2019) na klientských počítačích.

::: moniker-end

::: moniker range="vs-2017"

## <a name="step-1---download-visual-studio-product-files"></a>Krok 1: Stáhněte si soubory produktu Visual Studio

* [Vyberte úlohy a komponenty](workload-and-component-ids.md?view=vs-2017) , kterou chcete nainstalovat.

* [Vytvoření sdílené síťové složky pro soubory produktu Visual Studio](create-a-network-installation-of-visual-studio.md?view=vs-2017).

## <a name="step-2---build-an-installation-script"></a>Krok 2: vytvoření instalačního skriptu

* Vytváření instalačního skriptu, který používá [parametry příkazového řádku](use-command-line-parameters-to-install-visual-studio.md?view=vs-2017) řízení instalace.

  >[!NOTE]
  > Můžete zjednodušit pomocí skriptů [soubor odpovědí](automated-installation-with-response-file.md?view=vs-2017). Ujistěte se, že chcete vytvořit soubor odpovědí, který obsahuje výchozí možností instalace.

* (Volitelné) [Použít volume license product key](automatically-apply-product-keys-when-deploying-visual-studio.md?view=vs-2017) jako součást instalace skript tak, aby uživatelé nemuseli aktivovat software samostatně.

* (Volitelné) Aktualizace rozložení sítě, které [řídit, kdy a kde z produktu doručování aktualizací na vaše koncové uživatele](controlling-updates-to-visual-studio-deployments.md?view=vs-2017).

* (Volitelné) Nastavení zásad registru, které ovlivní také nasazení sady Visual Studio, jako je například, kde jsou nainstalovány některé balíčky sdílené s jinými verzemi nebo instance, [kde balíčky v mezipaměti](set-defaults-for-enterprise-deployments.md?view=vs-2019) nebo [Určuje, zda jsou balíčky v mezipaměti](disable-or-move-the-package-cache.md?view=vs-2017).

* (Volitelné) Nastavení zásad skupiny. Můžete také [konfigurace sady Visual Studio k zakázání zpětné vazby od zákazníků](../ide/visual-studio-experience-improvement-program.md) v jednotlivých počítačích.

## <a name="step-3---deploy"></a>Krok 3 – nasazení

* Zvolených technologií nasazení použijte ke spuštění skriptu na vaše cílové vývojářské pracovní stanice.

## <a name="step-4---deploy-updates"></a>Krok 4: nasazení aktualizací

* [Aktualizujte vaše umístění v síti s nejnovějšími aktualizacemi](update-a-network-installation-of-visual-studio.md?view=vs-2017) do sady Visual Studio spuštěním příkazu, který jste použili v kroku 1 v pravidelných intervalech a přidejte aktualizované součásti.

  Visual Studio můžete aktualizovat pomocí aktualizační skript. Chcete-li tak učinit, použijte [ `update` ](use-command-line-parameters-to-install-visual-studio.md?view=vs-2019) parametr příkazového řádku.

## <a name="step-5---optional-use-visual-studio-tools"></a>Krok 5: (volitelné) pomocí aplikace Visual Studio tools

Máme několik nástrojů, které vám pomůžou [zjišťovat a spravovat nainstalované instance sady Visual Studio](tools-for-managing-visual-studio-instances.md?view=vs-2017) na klientských počítačích.

::: moniker-end

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

* [Příklady parametrů příkazového řádku](command-line-parameter-examples.md)
* [Instalace certifikátů vyžadovaných pro offline instalace sady Visual Studio](install-certificates-for-visual-studio-offline.md)
* [Import a export konfigurace instalace](import-export-installation-configurations.md)
* [Archivy instalační program sady Visual Studio](https://devblogs.microsoft.com/setup/tag/vs2017/)
* [Životního cyklu produktu Visual Studio a údržba](/visualstudio/releases/2019/servicing/)
* [Synchronní autoload nastavení](../extensibility/synchronously-autoloaded-extensions.md)
