---
title: 'Postupy: Nahrazení parametrů v šabloně | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- template parameters, substituting
- Visual Studio templates, using parameters
ms.assetid: a62924a7-4ba0-413d-b606-fdbe1fcf2807
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 97a8a99e160e4d488e44cc9e084789fe3a005eb1
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54780288"
---
# <a name="how-to-substitute-parameters-in-a-template"></a>Postupy: Nahrazení parametrů v šabloně
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete nahradit parametry šablony, jako jsou názvy tříd a obory názvů, když soubor založený na šabloně je vytvořen. Úplný seznam parametrů šablony, najdete v části [parametry šablony](../ide/template-parameters.md).  
  
## <a name="procedure"></a>Postup  
 Pokaždé, když se vytvoří projekt na základě této šablony můžete nahradit parametry v souboru šablony. Tento postup vysvětluje, jak vytvořit šablonu, která se nahradí názvem oboru názvů bezpečný název projektu při vytvoření nového projektu pomocí šablony.  
  
#### <a name="to-use-a-parameter-to-replace-namespace-name-with-the-project-name"></a>Pomocí parametru nahradit název oboru názvů s názvem projektu  
  
1.  Vložte parametr v jednom nebo více souborů s kódem v šabloně. Příklad:  
  
    ```  
    namespace $safeprojectname$  
    ```  
  
    > [!NOTE]
    >  Parametry šablony jsou napsané ve formátu $*parametr*$.  
  
2.  V souboru .vstemplate šablony vyhledejte `ProjectItem` element, který obsahuje tento soubor.  
  
3.  Nastavte `ReplaceParameters` atribut `true` pro `ProjectItem` elementu. Příklad:  
  
    ```  
    <ProjectItem ReplaceParameters="true">Class1.cs</ProjectItem>  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)   
 [Parametry šablony](../ide/template-parameters.md)   
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [ProjectItem – element (šablony sady Visual Studio)](../extensibility/projectitem-element-visual-studio-item-templates.md)
