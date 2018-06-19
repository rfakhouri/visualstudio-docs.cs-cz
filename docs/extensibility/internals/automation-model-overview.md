---
title: Přehled modelu automatizace | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- automation [Visual Studio SDK], about automation
- extensibility
ms.assetid: 12b6d6db-0d22-4aaa-aa7d-1365f759b7b0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a9369bb6074bb294223051ba7dfa158648fe0cad
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31134744"
---
# <a name="automation-model-overview"></a>Přehled modelu automatizace
Model automatizace obsahuje sadu objektů, proti kterým může zapisovat na doplněk sady Visual Studio nebo příponu. Doplněk je aplikace, která můžete pracovat s prostředí Visual Studio a automatizaci běžných úkolů. Rozšíření sady Visual Studio můžete vytvořit vlastní součásti sady Visual Studio nebo přidat do funkce standardní komponenty, například textovém editoru.  
  
## <a name="objects-in-the-automation-model"></a>Objekty v modelu automatizace  
 Model automatizace se skládá z související skupiny objektů, které řídí hlavní omezující vlastnosti pro běžné prostředí. Toto je diagram, který zobrazuje rozsáhlou sadu objektů, které tvoří automatizace modelu.  
  
 ![Visual Studio automatizace objekt grafu](../../extensibility/internals/media/vsvisualstudioautomationobjectchart.gif "vsVisualStudioAutomationObjectChart")  
Objekty automatizace Visual Studio  
  
 Další informace najdete v tématu [rozšíření prostředí sady Visual Studio](http://msdn.microsoft.com/Library/4173a963-7ac7-4966-9bb7-e28a9d9f6792).  
  
 Prostředí poskytuje model pro různé oblasti, funkční. Například je model kódu pro různé prvky, které je možné, v kódu. Není model dokumentu pro různé prvky dokumentu. Jeden oblast, oblasti projektu je zajímají hlavně o VSPackage zprostředkovatele. Budete pravděpodobně chtít vaší nové typy projektu přispívat do modelu automatizace stejným způsobem jako [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] a [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] přispívat do modelu automatizace. Zda je proces uvedených v [poskytování automatizace pro VSPackages](../../extensibility/internals/providing-automation-for-vspackages.md).  
  
 Místa, kde můžete zvážit rozšíření modelu automatizace prostředí:  
  
-   Projekt  
  
-   Dokument  
  
-   Kód  
  
-   Sestavení  
  
 Další informace o automatizaci najdete v tématu [automatizace a rozšíření pro Visual Studio](http://msdn.microsoft.com/Library/f71a2253-3e68-4e5e-9a18-edbba816caf6). Tento dokument a dokumenty poskytuje odkazy na vám pomůže provádět rozhodnutí o tom, jak by měl poskytovat automatizace pro vaše VSPackage.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Vytvoření doplňku](http://msdn.microsoft.com/Library/50be56d2-e3a5-4cd2-8569-2a0666b268ce)