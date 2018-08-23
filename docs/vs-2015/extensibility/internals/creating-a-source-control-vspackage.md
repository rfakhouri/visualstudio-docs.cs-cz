---
title: Vytvoření ovládacího prvku VSPackage zdroje | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- source control [Visual Studio SDK], creating source control packages
- source control packages
ms.assetid: cca0a9ed-48ff-409f-8036-ed8db0f7533e
caps.latest.revision: 24
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e67d21fe906dd6bc2a1da0a7a483ee78aa0fe2db
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666586"
---
# <a name="creating-a-source-control-vspackage"></a>Vytvoření balíčku VSPackage správy zdrojového kódu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [vytváření VSPackage ovládací prvek zdroje](https://docs.microsoft.com/visualstudio/extensibility/internals/creating-a-source-control-vspackage).  
  
Tato dokumentace obsahuje odkazy na přehled architektury zdrojového balíčku integrovaná [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], rozhraní API, který je definován tak, že rozhraní k implementaci a služby, který se má používat a příklad, který znázorňuje jednoduchý zdroje balíček implementaci ovládacích prvků.  
  
 Pomocí správy zdrojového kódu VSPackage, můžete vytvořit cestu hluboká integrace správy zdrojového kódu pro integraci s [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Povoluje balíčku vynechat výchozí zdrojový ovládací prvek uživatelského rozhraní, které jsou hostovány [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], reagovat na požadavky ovládací prvek zdroje ze systému projektů a interakci s [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] komponenty, jako **Průzkumníka řešení**. [!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)] Umožňuje [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] spolupracuje s mechanismus pro vytvoření VSPackage, která lze integrovat s [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] pomocí modelu služby.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Začínáme](../../extensibility/internals/getting-started-with-source-control-vspackages.md)  
 Tento článek popisuje balíček zdrojového ovládacího prvku, který pokročilejší alternativu, která umožňuje pro implementaci funkce správy zdrojového kódu v modulu plug-in správy zdrojového kódu [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
 [Architektura](../../extensibility/internals/source-control-vspackage-architecture.md)  
 Uvede diagramu a vysvětluje součásti zdrojový balíček ovládacího prvku.  
  
 [Funkce](../../extensibility/internals/source-control-vspackage-features.md)  
 Popisuje různé funkce zdrojový balíček ovládacího prvku.  
  
 [Prvky návrhu](../../extensibility/internals/source-control-vspackage-design-elements.md)  
 Popisuje strukturu sady VSPackage, která zdrojový balíček ovládací prvek musí implementovat pro hluboká integrace.  
  
## <a name="related-sections"></a>Související oddíly  
 [Vytvoření modulu plug-in správy zdrojového kódu](../../extensibility/internals/creating-a-source-control-plug-in.md)  
 Tento článek popisuje postup vytvoření správy zdrojového kódu modulu plug-in, který poskytuje funkce správy zdrojového kódu v [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] zdrojového ovládacího prvku uživatelského rozhraní (UI).  
  
 [Správa zdrojového kódu](../../extensibility/internals/source-control.md)  
 Tento článek popisuje možnosti pro implementaci správy zdrojového kódu jako integrovaná funkce [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].

