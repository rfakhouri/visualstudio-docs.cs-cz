---
title: "Přepínače příkazového řádku nástroje DEVENV pro vývoj VSPackage | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- /setup command line switch
- /resetskippkgs command line switch
- /noVSIP command line switch
- /rootsuffix command line switch
- command-line switches
- registry, Visual Studio SDK
- command line, switches
- Visual Studio SDK, command-line switches
ms.assetid: d65d2c04-dd84-42b0-b956-555b11f5a645
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 18c531bb849793de184f3797067dceff4bd10199
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="devenv-command-line-switches-for-vspackage-development"></a>Přepínače příkazového řádku nástroje DEVENV pro vývoj VSPackage
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]umožňuje vývojářům k automatizaci úloh z příkazového řádku při provádění devenv.exe, soubor, který spustí integrované vývojové prostředí (IDE) sady Visual Studio.  
  
 Úkoly patří:  
  
-   Nasazení aplikací v předem navržených konfigurace z mimo prostředí IDE.  
  
-   Automatické vytváření projektů pomocí přednastavených nastavení sestavení nebo konfigurace ladění.  
  
-   Načítání IDE v konkrétní konfigurace z mimo prostředí IDE. Kromě toho můžete přizpůsobit IDE při spuštění.  
  
## <a name="guidelines-for-switches"></a>Pokyny pro přepínače  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]dokumentace popisuje příkazového řádku DEVENV úrovni uživatele. Další informace najdete v tématu [příkazového řádku DEVENV](../ide/reference/devenv-command-line-switches.md). DEVENV podporuje také další přepínače příkazového řádku, které jsou užitečné s VSPackage vývoj, nasazení a ladění.  
  
|Přepínač příkazového řádku|Popis|  
|--------------------------|-----------------|  
|/ safemode|Spustí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] v nouzovém režimu, načítání výchozí IDE a služby. Při načítání všech VSPackages třetích stran zabrání přepínač/safemode [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] spustí, čímž zajišťuje stabilní provádění.<br /><br /> Tento přepínač nezadávaly žádné argumenty.|  
|/resetskippkgs|Pak spustí vymaže všechny Přeskočit načítání možnosti, které byl přidán nástrojem Uživatelé, kteří chtějí předejít přetížení problematické VSPackages [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Přítomnost značku SkipLoading zakáže načítání VSPackage. Vymazání značky znovu povolí načítání VSPackage.<br /><br /> Tento přepínač nezadávaly žádné argumenty.|  
|/rootsuffix|Spustí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] pomocí alternativního umístění. Tento příkaz spustí zástupce vytvořené [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] instalační program:<br /><br /> exp /RootSuffix nástroje devenv<br /><br /> V takovém případě exp identifikuje umístění s konkrétní příponou, třeba 10.0Exp spíše než 10.0. Experimentální instanci umožňuje ladit nezávisle na instanci VSPackage [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] , že používáte psaní kódu.<br /><br /> Tento přepínač může trvat libovolný řetězec, který identifikuje umístění, které jste vytvořili pomocí VSRegEx.exe. Další informace najdete v tématu [experimentální instanci](../extensibility/the-experimental-instance.md).|  
|/Splash|Ukazuje [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] úvodní obrazovka obvyklým a poté zobrazí okno se zprávou před zobrazením hlavní IDE. Do pole zpráva umožňuje prostudovali úvodní obrazovka, chcete-li zkontrolovat na ikonu produktu VSPackage, například.<br /><br /> Tento přepínač nezadávaly žádné argumenty.|  
  
## <a name="see-also"></a>Viz také  
 [Přidání přepínače příkazového řádku](../extensibility/adding-command-line-switches.md)   
 [Devenv – přepínače příkazového řádku](../ide/reference/devenv-command-line-switches.md)