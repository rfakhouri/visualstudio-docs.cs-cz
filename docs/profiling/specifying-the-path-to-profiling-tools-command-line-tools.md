---
title: "Určení cesty k profilace nástroje příkazového řádku nástroje | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7047bf18-5779-4f6e-872c-66e2fc47c969
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d6b05de013143c1def53044a40977657fdd2cfcb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="specifying-the-path-to-profiling-tools-command-line-tools"></a>Určení cesty k nástrojům příkazového řádku pro profilaci
Cesta [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástroje příkazového řádku v nástrojích pro profilaci nebyla přidána do proměnné prostředí PATH. Na počítačích 32bitová verze nástroje jsou v jednom adresáři. Existují 32bitové a 64bitové verze nástrojů pro profilaci na 64bitových počítačích.  
  
## <a name="32-bit-computers"></a>32bitové počítače  
 Na 32bitové počítače, je výchozí adresář profileru nástroje *jednotka*\Program Files\Microsoft 11.0\Team Visual Studio Tools nástroje.  
  
## <a name="64-bit-computers"></a>64bitové počítače  
 Na 64bitových počítačích zadejte cestu podle cílové platformy PROFILOVANÉHO aplikace.  
  
-   Pro 32bitové aplikace je výchozí adresář profiler nástrojů:  
  
     *Jednotka*\Program soubory (x86) \Microsoft Visual Studio 11.0\Team nástroje nástroje  
  
-   Pro 64bitové aplikace je výchozí adresář profiler nástrojů:  
  
     *Jednotka*\Program soubory (x86) \Microsoft Visual Studio 11.0\Team nástroje Tools\x64