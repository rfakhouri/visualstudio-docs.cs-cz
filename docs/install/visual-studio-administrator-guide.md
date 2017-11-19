---
title: "Příručka správce Visual Studio | Microsoft Docs"
description: "Další informace o tom, jak nasadit sady Visual Studio v podnikovém prostředí."
ms.custom: 
ms.date: 05/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
ms.assetid: 4af353f5-6cfd-4ebe-bcfb-f42306e451a0
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 5d0f3e97f403bb7af144fad9e97afc932cdc6e83
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2017
---
# <a name="visual-studio-2017-administrator-guide"></a>Visual Studio 2017 Příručka správce

V podnikových prostředích je běžné pro správce systému pro nasazení instalace pro koncové uživatele v síťové sdílené složce nebo pomocí softwaru pro správu systému. Jsme jste chtěli modul Instalační program sady Visual Studio pro podporu podnikové nasazení umožňuje správcům systému schopnost vytvářet síťové umístění instalovat předem nakonfigurovat výchozí nastavení instalace, nasazení kódy product key během procesu instalace a po úspěšné zavedení spravovat aktualizace produktu. Tato příručka pro správce poskytuje pokyny na základě scénáře pro podnikové nasazení v síťovém prostředí.

## <a name="deploying-visual-studio-2017-in-an-enterprise-environment"></a>Nasazení v prostředí Visual Studio 2017

Visual Studio 2017 můžete nasadit do klientských pracovních stanic, dokud každý cílový počítač splňuje [minimální požadavky na instalaci](https://www.visualstudio.com/en-us/productinfo/vs2017-system-requirements-vs). Jestli nasazujete prostřednictvím softwaru, třeba System Center nebo dávkového souboru, budete obvykle chtít projít následující kroky:

1. [Vytvoření sdílené síťové složky, která obsahuje soubory produktu Visual Studio](create-a-network-installation-of-visual-studio.md) do umístění v síti.

2. [Vyberte komponenty a úlohy](workload-and-component-ids.md) chcete nainstalovat.

3. [Vytvořte soubor odpovědí](automated-installation-with-response-file.md) obsahující výchozí možnosti instalace. Nebo můžete taky [sestavení instalační skript](use-command-line-parameters-to-install-visual-studio.md) používající řízení instalace parametry příkazového řádku.

4. Volitelně můžete [použít volume license product key](automatically-apply-product-keys-when-deploying-visual-studio.md) jako součást instalace skript tak, aby uživatelé nepotřebují k aktivaci softwaru samostatně.

5. Síťový diagram pro aktualizace [řídit, kdy produktu aktualizace jsou doručovány na koncové uživatele](controlling-updates-to-visual-studio-deployments.md).

6. Volitelně můžete nastavit klíče registru [řídit, co se uloží do mezipaměti na klientských pracovních stanicích](set-defaults-for-enterprise-deployments.md).

7. Pomocí technologie nasazení podle volby pro spuštění skriptu vygenerované v předchozích krocích na pracovní stanice vývojáře cíl.

8. [Aktualizovat vaše umístění v síti s nejnovějšími aktualizacemi](update-a-network-installation-of-visual-studio.md) k sadě Visual Studio spuštěním příkazu, který jste použili v kroku 1 v pravidelných intervalech přidat aktualizované součásti.

> [!IMPORTANT]
> Všimněte si, že instalace ze sítě sdílenou složku se "nezapomeňte" umístění zdroje, že pochází od. To znamená, že jejich opravy klientský počítač může být nutné se vraťte do sdílené síťové složce, které klient původně nainstalované z. Pečlivě zvolte umístění v síti tak, aby se nastavuje zarovnání životního cyklu, které budete mít Visual Studio 2017 klientů se systémy ve vaší organizaci.

## <a name="visual-studio-tools"></a>Nástroje sady Visual Studio
Máme několik nástrojů, které vám pomůžou [zjišťovat a spravovat nainstalované sady Visual Studio instance](tools-for-managing-visual-studio-instances.md) na klientských počítačích.

> [!TIP]
> Kromě dokumentace v příručce správce, je dobré zdroj informací o instalaci Visual Studio 2017 [stavu Chmiela blog](https://blogs.msdn.microsoft.com/heaths/tag/vs2017/).

## <a name="get-support"></a>Získat podporu
V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránku Tipy pro odstraňování potíží. Taky můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj v prostředí Visual Studio IDE nebo ke sdílení návrh s nám na [UserVoice](https://visualstudio.uservoice.com/forums/121579). Můžete sledovat problémy produktu v [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/)a klást otázky a odpovědi. Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím našich [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio) (vyžaduje [Githubu](https://github.com/) účtu).

## <a name="see-also"></a>Viz také
* [Nainstalovat Visual Studio 2017](install-visual-studio.md)
* [Nainstalujte Visual Studio 2017 pomocí parametrů příkazového řádku](use-command-line-parameters-to-install-visual-studio.md)
  * [Příklady parametr příkazového řádku](command-line-parameter-examples.md)
  * [Referenční dokumentace úlohy a ID součásti](workload-and-component-ids.md)
* [Vytvořit založené na síti instalaci sady Visual Studio](create-a-network-installation-of-visual-studio.md)
  * [Instalace certifikátů vyžadovaných pro instalaci offline sady Visual Studio](install-certificates-for-visual-studio-offline.md)
* [Automatizovat Visual Studio se souborem odpovědí](automated-installation-with-response-file.md)
* [Automatické použití kódů product key při nasazení sady Visual Studio](automatically-apply-product-keys-when-deploying-visual-studio.md)
* [Výchozí nastavení pro nasazení v podnicích sady Visual Studio](set-defaults-for-enterprise-deployments.md)
* [Zakažte nebo přesunout do mezipaměti balíčku](disable-or-move-the-package-cache.md)
* [Aktualizace založené na síti instalace sady Visual Studio](update-a-network-installation-of-visual-studio.md)
* [Ovládací prvek aktualizací pro nasazení v sadě Visual Studio](controlling-updates-to-visual-studio-deployments.md)
* [Nástroje pro zjišťování a správu instancí sady Visual Studio](tools-for-managing-visual-studio-instances.md)
