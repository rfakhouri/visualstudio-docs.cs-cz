---
title: Usedcommand – Element | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- UsedCommands element (VSCT XML schema)
- VSCT XML schema elements, UsedCommands
ms.assetid: 99cd05d3-644a-42ff-b289-8458cd1b20c0
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: abcc3117b46cca424388b849f9baf26d79ca270e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49194635"
---
# <a name="usedcommand-element"></a>UsedCommand – element
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Umožňuje pro přístup k příkazu, který je definován v jiném souboru .vsct VSPackage. Například, pokud vaše VSPackage používá standardní **kopírování** příkaz, který je definovaný [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] prostředí, můžete přidat příkaz nabídky nebo panelu nástrojů bez znova implementovány.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<UsedCommand guid="guidMyCommandGroup" id="MyCommand" />  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|identifikátor GUID|Požadováno. Identifikátor GUID, které odpovídá páru ID identifikátoru GUID identifikující příkazu.|  
|id|Požadováno. ID, které odpovídá páru ID identifikátoru GUID identifikující příkazu.|  
|Podmínka|Volitelné. Zobrazit [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|Žádné||  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[UsedCommands – element](../extensibility/usedcommands-element.md)|Seskupí usedcommand – elementy a ostatní usedcommands – seskupení.|  
  
## <a name="remarks"></a>Poznámky  
 Přidáním příkazu, který bude `<UsedCommands>` informuje VSPackage elementu, [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] prostředí, že sady VSPackage vyžaduje, aby příkaz. Měli byste přidat `<UsedCommand>` – element pro kterýkoli příkaz vašeho balíčku vyžaduje, aby nemusí obsahovat všechny verze a konfigurace sady Visual Studio. Například pokud váš balíček volá příkaz, který je specifický pro aplikaci Visual C++, příkaz nebude dostupné uživatelům aplikace Visual Web Developer nezahrnete `<UsedCommand>` – element pro příkaz.  
  
## <a name="example"></a>Příklad  
  
```  
<UsedCommands>  
  <UsedCommand guid="guidVSStd97" id="cmdidCut"/>  
  <UsedCommand guid="guidVSStd97" id="cmdidCopy"/>  
  <UsedCommand guid="guidVSStd97" id="cmdidPaste"/>  
</UsedCommands>  
```  
  
## <a name="see-also"></a>Viz také  
 [Usedcommands – Element](../extensibility/usedcommands-element.md)   
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)

