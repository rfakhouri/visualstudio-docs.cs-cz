---
title: UsedCommand Element | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- UsedCommands element (VSCT XML schema)
- VSCT XML schema elements, UsedCommands
ms.assetid: 99cd05d3-644a-42ff-b289-8458cd1b20c0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4888733abf142f6582706406decbea0bf84ce519
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31139065"
---
# <a name="usedcommand-element"></a>UsedCommand Element
Umožňuje VSPackage k získání přístupu k příkazu, který je definován v jiném souboru .vsct. Například, pokud vaše VSPackage používá standardní **kopie** příkaz, který je definovaný [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] prostředí, můžete přidat příkaz nabídky nebo nástrojů bez implementace ho znovu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<UsedCommand guid="guidMyCommandGroup" id="MyCommand" />  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|Identifikátor GUID|Požadováno. Identifikátor GUID, které odpovídá páru GUID ID identifikující příkaz.|  
|id|Požadováno. ID pár ID identifikátor GUID, který identifikuje příkaz.|  
|Podmínka|Volitelné. V tématu [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|Žádné||  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[UsedCommands – element](../extensibility/usedcommands-element.md)|Elementy UsedCommand skupin a dalších UsedCommands seskupení.|  
  
## <a name="remarks"></a>Poznámky  
 Přidáním příkazu, který `<UsedCommands>` informuje VSPackage elementu, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] prostředí, VSPackage vyžaduje příkaz. Měli byste přidat `<UsedCommand>` element pro libovolný příkaz vašeho balíčku vyžaduje, aby nemusí obsahovat všechny verze a konfigurace sady Visual Studio. Například pokud váš balíček volá příkaz, který je specifický pro aplikaci Visual C++, příkaz nebude dostupný uživatelům aplikace Visual Web Developer nezahrnete `<UsedCommand>` element pro příkaz.  
  
## <a name="example"></a>Příklad  
  
```  
<UsedCommands>  
  <UsedCommand guid="guidVSStd97" id="cmdidCut"/>  
  <UsedCommand guid="guidVSStd97" id="cmdidCopy"/>  
  <UsedCommand guid="guidVSStd97" id="cmdidPaste"/>  
</UsedCommands>  
```  
  
## <a name="see-also"></a>Viz také  
 [UsedCommands Element](../extensibility/usedcommands-element.md)   
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)