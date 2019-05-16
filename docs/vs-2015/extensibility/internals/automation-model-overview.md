---
title: Přehled modelu automatizace | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- automation [Visual Studio SDK], about automation
- extensibility
ms.assetid: 12b6d6db-0d22-4aaa-aa7d-1365f759b7b0
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: e17164976062ec916074c6210be6ae42e8ea1d03
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65699516"
---
# <a name="automation-model-overview"></a>Přehled modelu automatizace
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Model automatizace se skládá sada objektů, u kterých můžete napsat doplňku sady Visual Studio nebo rozšíření. Doplněk je aplikace, která lze manipulovat s prostředí sady Visual Studio a automatizaci běžných úkolů. Rozšíření sady Visual Studio můžete vytvořit vlastní součásti sady Visual Studio nebo přidání funkcí standardní komponenty, jako je například textový editor.  
  
## <a name="objects-in-the-automation-model"></a>Objekty v modelu automatizace  
 Model automatizace se skládá z související skupiny objektů, které řídí hlavní charakteristiky společné prostředí. Tady je diagram, který zobrazuje rozsáhlou sadu objektů, které tvoří modelu automatizace.  
  
 ![Visual Studio Automation Object Chart](../../extensibility/internals/media/vsvisualstudioautomationobjectchart.gif "vsVisualStudioAutomationObjectChart")  
Objekty automatizace aplikace Visual Studio  
  
 Další informace najdete v tématu [rozšíření prostředí sady Visual Studio](https://msdn.microsoft.com/library/4173a963-7ac7-4966-9bb7-e28a9d9f6792).  
  
 Prostředí poskytuje model pro různé funkční oblasti. Například je model kódu pro různé prvky, které může vyhledávání v kódu. Existuje dokument model pro různé prvky dokumentu. Jednu oblast, oblast projektu je zajímavé především ke zprostředkovatelům VSPackage. Pravděpodobně budete nových typů projektů tak, abyste mohli přispívat do modelu automatizace stejným způsobem jako [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] a [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] přispívání do modelu automatizace. Aby proces je popsaný v [poskytování automatizace pro balíčky VSPackages](../../extensibility/internals/providing-automation-for-vspackages.md).  
  
 Místa, kde můžete zvážit rozšíření modelu automatizace prostředí:  
  
- Project  
  
- Dokument  
  
- Kód  
  
- Sestavení  
  
  Další informace o automatizaci, naleznete v tématu [automatizace a rozšiřitelnost sady Visual Studio](https://msdn.microsoft.com/library/f71a2253-3e68-4e5e-9a18-edbba816caf6). Tento dokument a dokumenty poskytuje odkazy na, vám pomůže rozhodnutí týkající se, jak by měl poskytování automatizace pro vaše VSPackage.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Vytvoření doplňku](https://msdn.microsoft.com/library/50be56d2-e3a5-4cd2-8569-2a0666b268ce)
