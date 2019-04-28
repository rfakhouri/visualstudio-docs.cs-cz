---
title: Rozšíření VSPackages a rozhraní Managed Package Framework | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: devlang-csharp
ms.topic: conceptual
helpviewer_keywords:
- managed package framework
- VSPackages, managed package framework
- managed VSPackages, managed package framework
ms.assetid: e8d80e0f-6b5b-4baf-a7df-59fd808c60cd
caps.latest.revision: 16
manager: jillfra
ms.openlocfilehash: 0b04692ed30e69e8904919748a6db0d0eff49f54
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63002114"
---
# <a name="vspackages-and-the-managed-package-framework"></a>Rozšíření VSPackages a rozhraní Managed Package Framework
Tím, že vytvoříte VSPackage spolu s balíčkem spravované třídy rozhraní framework (MPF) namísto pomocí třídy modelu COM interop můžete zkrátit dobu vývoje.  
  
 Existují dva způsoby vytvoření spravované VSPackage:  
  
- Použití [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] balíček šablony projektu  
  
     Další informace najdete v tématu [názorný postup: Vytvoření příkazu nabídky s použitím šablony sady Visual Studio balíček](http://msdn.microsoft.com/library/1985fa7d-aad4-4866-b356-a125b6a246de).  
  
- Vytvoření vašeho balíčku VSPackage bez [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] balíček šablony projektu  
  
     Například můžete zkopírovat ukázková VSPackage a změňte identifikátory GUID a názvů. Ukázky najdete v části VSX [Galerie kódu na](http://code.msdn.microsoft.com/vsx/).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Managed Package Framework třídy](../misc/managed-package-framework-classes.md)  
 Popisuje a obsahuje seznam oborů názvů MPF třídy a soubory DLL.  
  
## <a name="related-sections"></a>Související oddíly  
 [Návod: Vytvoření příkazu nabídky s použitím balíčku šablony sady Visual Studio](http://msdn.microsoft.com/library/1985fa7d-aad4-4866-b356-a125b6a246de)  
 Vysvětluje, jak vytvořit spravovaný VSPackage.  
  
 [Spravovaná rozšíření VSPackages](../misc/managed-vspackages.md)  
 Zavádí aspekty rozšíření VSPackages, které platí pro spravovaný kód.