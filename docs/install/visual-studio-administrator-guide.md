---
title: Příručka správce Visual Studio
description: Další informace o tom, jak nasadit sady Visual Studio v podnikovém prostředí.
ms.custom: ''
ms.date: 05/29/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
ms.assetid: 4af353f5-6cfd-4ebe-bcfb-f42306e451a0
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0436612d208fa4ffbcc808007849b5d168b049da
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34691115"
---
# <a name="visual-studio-2017-administrator-guide"></a>Visual Studio 2017 Příručka správce

V podnikových prostředích je běžné pro správce systému pro nasazení instalace pro koncové uživatele v síťové sdílené složce nebo pomocí softwaru pro správu systému. Jsme jste chtěli modul Instalační program sady Visual Studio pro podporu podnikové nasazení umožňuje správcům systému schopnost vytvářet síťové umístění instalovat předem nakonfigurovat výchozí nastavení instalace, nasazení kódy product key během procesu instalace a po úspěšné zavedení spravovat aktualizace produktu. Tato příručka pro správce poskytuje pokyny na základě scénáře pro podnikové nasazení v síťovém prostředí.

## <a name="deploy-visual-studio-2017-in-an-enterprise-environment"></a>Nasazení v prostředí Visual Studio 2017

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

## <a name="use-visual-studio-tools"></a>Pomocí nástrojů Visual Studio

Máme několik nástrojů, které vám pomůžou [zjišťovat a spravovat nainstalované sady Visual Studio instance](tools-for-managing-visual-studio-instances.md) na klientských počítačích.

> [!TIP]
> Kromě dokumentace v příručce správce, je dobré zdroj informací o instalaci Visual Studio 2017 [stavu Chmiela blog](https://blogs.msdn.microsoft.com/heaths/tag/vs2017/).

## <a name="specify-customer-feedback-settings"></a>Zadejte nastavení zpětné vazby zákazníka

Ve výchozím nastavení povoluje instalaci sady Visual Studio názory zákazníků. Když povolíte zásad skupiny, můžete nakonfigurovat Visual Studio zakázat názory zákazníků na jednotlivých počítačích. Uděláte to tak nastavte zásady založenou na registru na následující klíč:

**HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\VisualStudio\SQM**

Položka = **OptIn**

Hodnota = (DWORD)
* **0** je používání
* **1** bude poskytnut souhlas

Další informace o nastavení zpětné vazby zákazníka najdete v tématu [programu zlepšování zkušeností zákazníků sady Visual Studio](../ide/visual-studio-experience-improvement-program.md) stránky.

## <a name="get-support"></a>Získat podporu

V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránky. Pokud se žádný z kroků pro řešení potíží, kontaktujte nás pomocí živé konverzace pro pomoc s instalací (pouze v angličtině). Podrobnosti najdete v tématu [stránky podpory sady Visual Studio](https://www.visualstudio.com/vs/support/#talktous).

Tady je několik další možnosti podpory:

* Můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémy produktu a najít v odpovědi [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/).
* Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio). (Tato možnost vyžaduje [Githubu](https://github.com/) účtu.)

## <a name="see-also"></a>Viz také:

* [Nainstalovat Visual Studio 2017](install-visual-studio.md)
* [Nainstalujte Visual Studio 2017 pomocí parametrů příkazového řádku](use-command-line-parameters-to-install-visual-studio.md)
  * [Příklady parametrů příkazového řádku](command-line-parameter-examples.md)
  * [Referenční dokumentace úlohy a ID součásti](workload-and-component-ids.md)
* [Vytvořit založené na síti instalaci sady Visual Studio](create-a-network-installation-of-visual-studio.md)
  * [Instalace certifikátů vyžadovaných pro instalaci offline sady Visual Studio](install-certificates-for-visual-studio-offline.md)
* [Automatizovat Visual Studio se souborem odpovědí](automated-installation-with-response-file.md)
* [Automatické použití kódů Product Key při nasazení sady Visual Studio](automatically-apply-product-keys-when-deploying-visual-studio.md)
* [Nastavení výchozích hodnot pro podniková nasazení sady Visual Studio](set-defaults-for-enterprise-deployments.md)
* [Zakázání nebo přesunutí mezipaměti balíčku](disable-or-move-the-package-cache.md)
* [Aktualizace založené na síti instalace sady Visual Studio](update-a-network-installation-of-visual-studio.md)
* [Řízení aktualizací nasazení sady Visual Studio](controlling-updates-to-visual-studio-deployments.md)
* [Nástroje pro zjišťování a správu instancí sady Visual Studio](tools-for-managing-visual-studio-instances.md)
