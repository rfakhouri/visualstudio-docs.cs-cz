---
title: Vnoření projektů | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project nesting
- nested projects
- projects [Visual Studio SDK], child projects
- projects [Visual Studio SDK], nesting
ms.assetid: 12cce037-9840-4761-845e-5abd5fb317b0
caps.latest.revision: 16
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 0e3a0fae42dc7bf1497e3d0d4a9d23f9cab50675
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54757044"
---
# <a name="nesting-projects"></a>Vnoření projektů
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vývojářům aplikací pro podniky, které používají váš balíček VS můžete pohodlně Seskupit podobné typy projektů společně v [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] pomocí *projektu vnoření*. Projekt šablony organizace například používá vnořené projekty do skupiny projektů do kategorií. Projekty Business průčelí, projekty webového uživatelského rozhraní a podobně jsou seskupeny dohromady v jedné kategorii.  
  
 V tomto scénáři neexistuje žádné omezení počtu projekty, které může vývojář vnořené do každý nadřazený projekt, i když vývojář můžete programově zadat omezení. Tento typ seskupení lze provést také rekurzivní, v takovém případě projekty stejného typu jako podřízený projekt mohou být vnořené pod podřízené se dílčí projekt podřízené, což je dílčí projekt nadřazeného prvku.  
  
 Vnoření projektů není vnitřní součástí [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Je nutné napsat kód pro povolení vnořené a dílčí projekt vnoření v rámci podřízené projekty. Nadřazený projekt je speciální VSPackage, nebo typ projektu, vytvořen a zaregistrován s vlastní identifikátor GUID, který obsahuje kód, který se vyžaduje k implementaci projektu vnoření.  
  
 Příklad vnořených projektů najdete v ukázce Example.Nested projektu C#.  
  
## <a name="nested-projects-example"></a>Příklad vnořených projektů  
 ![Vnořené projekty řešení](../../extensibility/internals/media/vsnestedprojects.gif "vsNestedProjects")  
Příklad vnořených projektů  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Implementace vnořených projektů](../../extensibility/internals/how-to-implement-nested-projects.md)   
 [Důležité informace pro uvolnění a opětovné načtení vnořených projektů](../../extensibility/internals/considerations-for-unloading-and-reloading-nested-projects.md)   
 [Podpora průvodce pro vnořené projekty](../../extensibility/internals/wizard-support-for-nested-projects.md)   
 [Registrace šablon projektů a položek](../../extensibility/internals/registering-project-and-item-templates.md)   
 [Implementace zpracování příkazů pro vnořené projekty](../../extensibility/internals/implementing-command-handling-for-nested-projects.md)   
 [Filtrování dialogového okna pro vnořené projekty](../../extensibility/internals/filtering-the-additem-dialog-box-for-nested-projects.md)   
 [Kontrolní seznam: Vytvoření nových typů projektů](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [Kontextové parametry](../../extensibility/internals/context-parameters.md)   
 [Soubor průvodce (.Vsz)](../../extensibility/internals/wizard-dot-vsz-file.md)
