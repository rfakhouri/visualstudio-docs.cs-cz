---
title: UsedCommand Element | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UsedCommands element (VSCT XML schema)
- VSCT XML schema elements, UsedCommands
ms.assetid: 99cd05d3-644a-42ff-b289-8458cd1b20c0
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2b3974c9103a385badc56fda759ee95ef3a40a93
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
|[UsedCommands Element](../extensibility/usedcommands-element.md)|Elementy UsedCommand skupin a dalších UsedCommands seskupení.|  
  
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
 [Visual Studio příkaz tabulky (. Soubory Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)