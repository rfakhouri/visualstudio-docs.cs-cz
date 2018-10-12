---
title: Určení cesty k profilování nástroje příkazového řádku nástroje | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7047bf18-5779-4f6e-872c-66e2fc47c969
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 407ed292bea2b6b7b47e07a3a5e30183f411f991
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49242902"
---
# <a name="specifying-the-path-to-profiling-tools-command-line-tools"></a>Určení cesty k nástrojům příkazového řádku pro profilaci
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Cesta k [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] příkazového řádku nástrojů pro profilaci není přidán do proměnné prostředí PATH. Na 32bitových počítačích nástroje jsou v jednom adresáři. Existují 32bitové a 64bitové verze nástrojů pro profilaci na 64bitových počítačích.  
  
## <a name="32-bit-computers"></a>32bitových počítačích  
 Na 32bitových počítačích, je výchozí adresář nástrojů profilování *jednotka*\Program Files\Microsoft 11.0\Team nástroje nástroje Visual Studio.  
  
## <a name="64-bit-computers"></a>64bitové počítače  
 Na 64bitových počítačích zadejte cestu podle cílové platformy profilované aplikace.  
  
-   Pro 32bitové aplikace je výchozí adresář nástrojů profilování:  
  
     *Jednotka*\Program soubory (x86) \Microsoft Visual Studio 11.0\Team nástroje nástroje  
  
-   Pro 64bitové aplikace je výchozí adresář nástrojů profilování:  
  
     *Jednotka*\Program soubory (x86) \Microsoft Visual Studio 11.0\Team nástroje Tools\x64



