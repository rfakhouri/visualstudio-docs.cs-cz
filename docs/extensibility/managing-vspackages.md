---
title: "Správa VSPackages | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSPackages, autoloading
- VSPackages, delayed loading
- delay loading
- VSPackages, loading
ms.assetid: 386e0ce5-4107-4164-b0cd-1cf43eb5e7cf
caps.latest.revision: "35"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 55ba59a5a29181dfa3cdd70427720293582a648d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="managing-vspackages"></a>Správa VSPackages
Ve většině případů nemusíte si dělat starosti o správě VSPackages, protože šablon projektů a položek registraci a automaticky načíst balíček. V některých případech můžete však zjistěte chvilku další, abyste mohli spravovat váš balíček.  
  
## <a name="using-the-experimental-instance"></a>Pomocí experimentální instanci  
 Další informace o experimentální instanci, najdete v tématu [experimentální instanci](../extensibility/the-experimental-instance.md).  
  
## <a name="registering-and-unregistering-vspackages"></a>Registrace a zrušení registrace VSPackages  
 Způsob registrace a zrušení registrace VSPackages a dalších typů rozšíření naleznete v tématu [registrace a zrušení registrace VSPackages](../extensibility/registering-and-unregistering-vspackages.md).  
  
## <a name="loading-a-vspackage"></a>Načítání VSPackage  
 VSPackages může být nastaven na autoload při konkrétní CMDUICONTEXT GUID zapnutá. Další informace najdete v tématu [načítání VSPackages](../extensibility/loading-vspackages.md).  
  
## <a name="using-asyncpackage-to-load-vspackages-in-the-background"></a>Pomocí AsyncPackage načíst VSPackages na pozadí  
 Třída AsyncPackage umožňuje balíček načítání na pozadí vlákno pro lepší odezvy uživatelského rozhraní v sadě Visual Studio. Další informace najdete v tématu [postupy: použití AsyncPackage k VSPackages zatížení na pozadí](../extensibility/how-to-use-asyncpackage-to-load-vspackages-in-the-background.md).  
  
## <a name="rule-based-ui-context-for-extensions"></a>Kontext založený na pravidlech uživatelského rozhraní pro rozšíření  
 Kontexty založeného na pravidlech uživatelského rozhraní umožňuje autorům rozšíření zadat přesné podmínky, za které se aktivuje kontextu uživatelského rozhraní a přidružené VSPackages načíst. Další informace najdete v tématu [postupy: použití pravidla na základě kontextu uživatelského rozhraní pro rozšíření Visual Studia](../extensibility/how-to-use-rule-based-ui-context-for-visual-studio-extensions.md).  
  
## <a name="diagnosing-extension-performance"></a>Diagnostikování rozšíření výkonu  
Rozšíření může ovlivnit výkon zatížení spuštění a řešení. Zjistěte, jak se počítá dopad rozšíření sady Visual Studio a jak lze analyzovat lokálně otestovat, pokud rozšíření se může zobrazit jako rozšíření, které mají vliv výkon. Další informace najdete v tématu [postupy: diagnostikování výkonu rozšíření](how-to-diagnose-extension-performance.md). 
  
## <a name="troubleshooting-vspackages"></a>Řešení potíží s VSPackages  
 Zjistit techniky pro řešení potíží s VSPackages, který Nenačítat nebo výskytu chyb: [VSPackages řešení potíží](../extensibility/troubleshooting-vspackages.md)  
  
## <a name="see-also"></a>Viz také  
 [VSPackages](../extensibility/internals/vspackages.md)