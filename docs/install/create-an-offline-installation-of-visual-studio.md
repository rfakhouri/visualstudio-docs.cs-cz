---
title: Vytvoření Offline instalace sady Visual Studio
description: Zjistěte, jak v režimu offline instalace sady Visual Studio.
ms.custom: ''
ms.date: 01/17/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- offline installation [Visual Studio]
- offline install [Visual Studio]
- layout [Visual Studio]
ms.assetid: f8625d5e-f6ea-4db0-83c0-619b77fab3cf
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d19eabe10234ca2a1670ae04f99a45a85a6cac14
ms.sourcegitcommit: 6b092e7d466377f06913d49d183dbbdca16730f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/28/2018
ms.locfileid: "43138874"
---
# <a name="create-an-offline-installation-of-visual-studio-2017"></a>Vytvoření offline instalace sady Visual Studio 2017

Jsme navrhovali instalačního programu sady Visual Studio 2017 dobře fungovaly v nejrůznějších podmínek sítě a počítače.

- Nový model založený na úlohách znamená, že budete muset stáhnout úplně menší než v předchozích verzích sady Visual Studio: pouhých 300 MB nejmenší instalace;
- Ve srovnání s obecný "ISO" nebo soubor zip, se nám stáhnout pouze balíčky, které potřebujete pro svůj počítač. Například můžeme nestahovat 64-bit soubory Pokud nepotřebujete.
- Během procesu instalace snažíme tři různé stahování technologie (WebClient, BITŮ a WinInet) bránila v softwaru antivirový program a proxy serveru.
- Soubory je potřeba nainstalovat sadu Visual Studio se distribuují na síť pro doručování globální, abychom se mohli je pro vás z místního serveru.

Doporučujeme vám vyzkoušet [webovou Instalační službu sady Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)&mdash;myslíme si, zjistíte to kvalitní prostředí.

 > [!div class="button"]
 > [Stažení sady Visual Studio 2017](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

Pokud chcete nainstalovat do offline režimu, protože připojení k Internetu je nedostupné nebo nespolehlivé, viz [instalace sady Visual Studio 2017 v pomalé nebo nespolehlivé síti prostředí](../install/install-vs-inconsistent-quality-network.md). Chcete-li vytvořit místní mezipaměti soubory, které potřebujete k dokončení offline instalace můžete použít příkazový řádek. Tento proces nahradí soubory ISO k dispozici pro předchozí verze.

> [!NOTE]
> Pokud jste správce organizace, který chce provést nasazení sady Visual Studio 2017 k síti klientských pracovních stanic, které jsou aplikována brána firewall z Internetu, najdete v našich [vytvoření síťové instalace sady Visual Studio 2017](../install/create-a-network-installation-of-visual-studio.md) a [Instalaci certifikátů vyžadovaných pro offline instalace sady Visual Studio](../install/install-certificates-for-visual-studio-offline.md) stránky.

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]
