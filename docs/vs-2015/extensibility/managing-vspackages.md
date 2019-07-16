---
title: Správa rozšíření VSPackages | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, autoloading
- VSPackages, delayed loading
- delay loading
- VSPackages, loading
ms.assetid: 386e0ce5-4107-4164-b0cd-1cf43eb5e7cf
caps.latest.revision: 36
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 0b56ab490342cfbda9c16408aa0937abd80728c9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68194375"
---
# <a name="managing-vspackages"></a>Správa rozšíření VSPackages
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Ve většině případů nemusíte starat o správu rozšíření VSPackages, protože šablony projektů a položek registrovat a automaticky načíst balíček. Ale v některých případech budete muset naučit něco, aby správu balíčků.  
  
## <a name="using-the-experimental-instance"></a>Používáte-li experimentální instanci  
 Další informace o experimentální instanci najdete v tématu [experimentální instanci](../extensibility/the-experimental-instance.md).  
  
## <a name="registering-and-unregistering-vspackages"></a>Registrace a zrušení registrace rozšíření VSPackages  
 Jak vytvářet a rušit registraci rozšíření VSPackages a jinými typy rozšíření najdete v tématu [registrace a zrušení registrace rozšíření VSPackages](../extensibility/registering-and-unregistering-vspackages.md).  
  
## <a name="loading-a-vspackage"></a>Načítání VSPackage  
 Rozšíření VSPackages lze nastavit na autoload Pokud konkrétní identifikátor GUID CMDUICONTEXT zapnutá. Další informace najdete v tématu [načítání rozšíření VSPackages](../extensibility/loading-vspackages.md).  
  
## <a name="using-asyncpackage-to-load-vspackages-in-the-background"></a>Použití AsyncPackage k načtení rozšíření VSPackages na pozadí  
 Třída AsyncPackage umožňuje balíček načítání ve vlákně na pozadí pro lepší odezvy uživatelského rozhraní v sadě Visual Studio. Další informace najdete v tématu [jak: Použití AsyncPackage k načtení rozšíření VSPackages na pozadí](../extensibility/how-to-use-asyncpackage-to-load-vspackages-in-the-background.md).  
  
## <a name="rule-based-ui-context-for-extensions"></a>Kontext založený na pravidlech uživatelského rozhraní pro rozšíření  
 Kontexty uživatelského rozhraní založeného na pravidlech umožňuje autorům rozšíření určit přesné podmínky, za kterých se aktivuje kontextu uživatelského rozhraní a načíst přidružené balíčky VSPackages. Další informace najdete v tématu [jak: Použití kontextu uživatelského rozhraní založeného na pravidlo pro rozšíření sady Visual Studio](../extensibility/how-to-use-rule-based-ui-context-for-visual-studio-extensions.md).  
  
## <a name="troubleshooting-vspackages"></a>Řešení potíží s rozšířením VSPackages  
 Přečtěte si techniky pro řešení potíží s rozšířením VSPackages, který se nenačtou nebo dochází k chybám: [Řešení potíží s rozšířením VSPackages](../extensibility/troubleshooting-vspackages.md)  
  
## <a name="see-also"></a>Viz také  
 [Balíčky VSPackage](../extensibility/internals/vspackages.md)
