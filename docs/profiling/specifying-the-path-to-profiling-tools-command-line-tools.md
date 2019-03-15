---
title: Určení cesty k profilování nástroje příkazového řádku nástroje | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 7047bf18-5779-4f6e-872c-66e2fc47c969
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 03b11b478ef441dc7a09902a7185bfdf45e20dc3
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57868947"
---
# <a name="specify-the-path-to-profiling-tools-command-line-tools"></a>Zadejte cestu k nástrojům příkazového řádku pro profilaci

Cesta k [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] příkazového řádku nástrojů pro profilaci není přidán do proměnné prostředí PATH. Na 32bitových počítačích nástroje jsou v jednom adresáři. Existují 32bitové a 64bitové verze nástrojů pro profilaci na 64bitových počítačích.

## <a name="32-bit-computers"></a>32bitových počítačích
::: moniker range=">=vs-2019"
 Pro nativní kód profileru sady Visual Studio rozhraní API jsou v *VSPerf.dll*. Soubor hlaviček *VSPerf.h*a knihovnu importu *VSPerf.lib*, jsou umístěny v *Microsoft Visual Studio\2019\Team nástroje Tools\PerfSDK* adresář.
::: moniker-end
::: moniker range="vs-2017"
 Pro nativní kód profileru sady Visual Studio rozhraní API jsou v *VSPerf.dll*. Soubor hlaviček *VSPerf.h*a knihovnu importu *VSPerf.lib*, jsou umístěny v *Microsoft Visual Studio\2017\Team nástroje Tools\PerfSDK* adresář.
::: moniker-end

 Pro spravovaný kód, okna profilování rozhraní API jsou v *Microsoft.VisualStudio.Profiler.dll*. Tato knihovna DLL se nachází v *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools* adresáře.

## <a name="64-bit-computers"></a>64bitové počítače

Na 64bitových počítačích zadejte cestu podle cílové platformy profilované aplikace.

::: moniker range=">=vs-2019"
-   Pro 32bitové aplikace je výchozí adresář nástrojů profilování:

     (nativní) *Microsoft Visual Studio\2019\Team nástroje Tools\PerfSDK* (spravované) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools*

-   Pro 64bitové aplikace je výchozí adresář nástrojů profilování:

     (nativní) *Microsoft Visual Studio\2019\Team nástroje Tools\x64\PerfSDK* (spravované) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools\x64*
::: moniker-end

::: moniker range="vs-2017"
-   Pro 32bitové aplikace je výchozí adresář nástrojů profilování:

     (nativní) *Microsoft Visual Studio\2017\Team nástroje Tools\PerfSDK* (spravované) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools*

-   Pro 64bitové aplikace je výchozí adresář nástrojů profilování:

     (nativní) *Microsoft Visual Studio\2017\Team nástroje Tools\x64\PerfSDK* (spravované) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools\x64*
::: moniker-end