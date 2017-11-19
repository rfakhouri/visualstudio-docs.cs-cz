---
title: VisibilityItem Element | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VisibilityItem element (VSCT XML schema)
- VSCT XML schema elements, VisibilityItem
ms.assetid: 0932f551-972d-4194-84bb-426e3e4375e4
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: db041f839e9b7e8ad3268175829ecfee9380e736
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="visibilityitem-element"></a>VisibilityItem Element
`VisibilityItem` Element určuje, zda se statický příkazů a panely nástrojů. Každá položka identifikuje příkaz nebo nabídky a také kontextu přidružený příkaz uživatelského rozhraní. Sada Visual Studio zjistí příkazy, nabídek a panelů nástrojů a jejich viditelnost bez načítání VSPackages, který je definovat. Rozhraní IDE používá <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A> metoda k určení, zda kontext uživatelského rozhraní příkazů je aktivní.  
  
 Po načtení VSPackage Visual Studio očekává příkaz viditelnost bude určen VSPackage místo `VisibilityItem`. Pokud chcete určit viditelnost váš příkaz, můžete implementovat buď <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> obslužné rutiny události nebo <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metoda, v závislosti na tom, jak jste implementovali příkazu.  
  
 Příkaz nebo nabídky, který má `VisibilityItem` prvek se zobrazuje pouze v případě, přidružené kontextu je aktivní. K nejméně jeden příkaz uživatelského rozhraní kontext zahrnutím záznam pro každou kombinaci kontext příkazů můžete přidružit jeden příkaz, nabídky nebo panelu nástrojů. Pokud příkaz nebo nabídky je přidružen více kontexty uživatelského rozhraní příkaz, příkaz nebo nabídky je viditelná při aktivním některého kontextů přidružený příkaz uživatelského rozhraní.  
  
 `VisibilityItem` Element se vztahuje pouze na příkazy, nabídek a panelů nástrojů, ne do skupin. Element, který nemá se souvisejícím `VisibilityItem` je element viditelný vždy, když jeho nadřazený nabídky je aktivní.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<VisibilityItem  
  guid ="="cmdGuidMyProductCommands"  
  id=="cmdidAddWidget"  
  context="guidNotViewSourceMode"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|Identifikátor GUID|Požadováno. Identifikátor GUID identifikátor GUID nebo ID příkazu.|  
|id|Požadováno. ID identifikátor GUID nebo ID příkazu.|  
|kontext|Požadováno. Kontext uživatelského rozhraní, ve kterém se příkaz viditelné.|  
|Podmínka|Volitelné. V tématu [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[VisibilityConstraints Element](../extensibility/visibilityconstraints-element.md)|`VisibilityConstraints` Element určuje, zda se statických skupin příkazů a panely nástrojů.|  
  
## <a name="remarks"></a>Poznámky  
 Standardní rozhraní Visual Studia kontexty jsou definovány v *cesta instalace Visual Studio SDK*\VisualStudioIntegration\Common\Inc\vsshlids.h souboru stejně jako v <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids> a <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80> třídy. Více kompletní sadu kontexty uživatelského rozhraní je definována v <xref:Microsoft.VisualStudio.VSConstants> třídy.  
  
## <a name="example"></a>Příklad  
  
```  
<VisibilityConstraints>  
  <VisibilityItem guid="cmdSetGuidMyProductCommands"     id="cmdidAddWidget"  
    context="guidNotViewSourceMode"/>  
</VisibilityConstraints>  
```  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A>   
 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus>   
 <xref:Microsoft.VisualStudio.VSConstants>   
 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids>   
 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80>   
 [VisibilityConstraints Element](../extensibility/visibilityconstraints-element.md)   
 [Visual Studio příkaz tabulky (. Soubory Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)