---
title: "Součásti správy | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- installation [Visual Studio SDK], components
- installation [Visual Studio SDK], file management
ms.assetid: 029bffa2-6841-4caa-a41a-442467e1aedc
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 73a3100252dd5ddfcebd791588a4041c8d588e8d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="component-management"></a>Součásti správy
Jednotky úloh v instalační služby systému Windows se označují jako součásti Instalační služby systému Windows (někdy nazývané WICs nebo jenom komponenty). Identifikátor GUID identifikuje každého WIC, což je základní jednotkou instalace a pro nastavení, která pomocí Instalační služby systému Windows při počítání referencí.  
  
 Přestože několik produktů je možné použít k vytvoření instalačním programem vaší VSPackage, tento postup předpokládá použití souborů Instalační služby systému Windows (.msi). Při vytváření instalačním programem vaší, je třeba správně spravovat nasazení souborů tak, aby správný referenční počítání se stane po celou dobu. V důsledku toho různé verze produktu nebude narušovat nebo přerušení navzájem v poměru instalace a odinstalace scénáře.  
  
 Instalační služba systému Windows počítání odkazů dochází na úrovni součásti. Musíte pečlivě uspořádání prostředků – soubory, položky registru a tak dále – do součásti. Existují další úrovně organizace, jako jsou moduly, funkce a produkty –, které mohou pomoci v různých scénářích. Další informace najdete v tématu [základy Instalační služby systému Windows](../../extensibility/internals/windows-installer-basics.md).  
  
## <a name="guidelines-of-authoring-setup-for-side-by-side-installation"></a>Pokyny k vytváření, instalační program pro instalaci vedle sebe  
  
-   Autor soubory a klíče registru, které jsou sdíleny mezi verzemi do svých vlastních součásti.  
  
     To umožňuje snadno je můžou využívat v příští verzi. Knihovny typů, které jsou registrovány globálně, například souboru rozšíření, další položky registrované v HKEY_CLASSES_ROOT a tak dále.  
  
-   Sdílení součástí skupiny do samostatné slučovacích modulů.  
  
     To pomůže vytvořit správně pro souběžného postoupíte.  
  
-   Instalace sdílené soubory a klíče registru pomocí stejné součásti Instalační služby systému Windows mezi verzemi.  
  
     Pokud chcete použít jinou součást, soubory a položky registru jsou odinstalovat, pokud jeden verzí VSPackage je odinstalována, ale jiné VSPackage je stále nainstalován.  
  
-   Nemíchat verzí a sdílené položky do stejné komponenty.  
  
     Díky tomu znemožňuje nainstalovat sdílené položky do globální umístění a verzí položek izolované umístění.  
  
-   Nemají klíče registru sdílené, které odkazují na verzí souborů.  
  
     Pokud tak učiníte, přepíšou se při instalaci jinou verzí VSPackage sdílených klíčů. Po odebrání druhá verze souboru, na kterou odkazuje klíč je pryč.  
  
## <a name="see-also"></a>Viz také  
 [Volba mezi VSPackages sdílené a verzí](../../extensibility/choosing-between-shared-and-versioned-vspackages.md)   
 [Instalační program VSPackage scénáře](../../extensibility/internals/vspackage-setup-scenarios.md)