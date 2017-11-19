---
title: "Postupy: nahrazení parametrů v šabloně | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- template parameters, substituting
- Visual Studio templates, using parameters
ms.assetid: a62924a7-4ba0-413d-b606-fdbe1fcf2807
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e6e13e704502443c371021c515c7a9578497f829
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-substitute-parameters-in-a-template"></a>Postupy: Nahrazení parametrů v šabloně
Můžete nahradit parametry šablony například názvy tříd a obory názvů, pokud soubor na základě šablony je vytvořen. Úplný seznam parametrů šablony, najdete v části [parametry šablony](../ide/template-parameters.md).  
  
## <a name="procedure"></a>Postup  
 Při každém projektu, na základě této šablony můžete nahradit parametry v souborech šablony. Tento postup vysvětluje, jak vytvořit šablonu, která nahradí název oboru názvů bezpečný název projektu při vytvoření nového projektu pomocí šablony.  
  
#### <a name="to-use-a-parameter-to-replace-namespace-name-with-the-project-name"></a>Pomocí parametru nahradit název oboru názvů název projektu  
  
1.  Vložte parametr v jednom nebo více souborů kódu v šabloně. Příklad:  
  
    ```  
    namespace $safeprojectname$  
    ```  
  
    > [!NOTE]
    >  Parametry šablony jsou zapsány ve formátu $*parametr*$.  
  
2.  V souboru .vstemplate pro šablonu, vyhledejte `ProjectItem` element, který obsahuje tento soubor.  
  
3.  Nastavte `ReplaceParameters` atribut `true` pro `ProjectItem` elementu. Příklad:  
  
    ```  
    <ProjectItem ReplaceParameters="true">Class1.cs</ProjectItem>  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)   
 [Parametry šablony](../ide/template-parameters.md)   
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [ProjectItem – Element (šablony sady Visual Studio položky)](../extensibility/projectitem-element-visual-studio-item-templates.md)