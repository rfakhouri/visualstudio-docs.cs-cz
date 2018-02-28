---
title: "Příkazy Element | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Commands
helpviewer_keywords:
- Commands element (VSCT XML schema)
- VSCT XML schema elements, Commands
ms.assetid: 47cf16a5-d78b-452e-86f6-b5893856dddf
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 7c5cce390ad786ad530153e1850850509990b039
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="commands-element"></a>Element příkazy
Představuje kolekci příkazů na panelu nástrojů VSPackage. Kolekce může mít až pět témata, následujícím způsobem: nabídky, skupiny, tlačítek, kláves a rastrové obrázky.  
  
 Každý část podřízený element, například \<nabídky >, je identifikovaný příkaz jedinečné ID, které je číselný identifikátor dvojice a identifikátor GUID. Identifikátor GUID identifikuje sadu příkazů"" a slouží k seskupení logicky spojených příkazy. VSPackage měli definovat vlastní sadu pro zabránění kolizím s identifikátory příkazů, které jsou definované za jiných VSPackages příkazů.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Commands package="GuidMyPackage" >  
  <Menus>... </Menus>  
  <Groups>... </Groups>  
  <Buttons>... </Buttons>  
  <Combos>... </Combos>  
  <Bitmaps>... </Bitmaps>  
</Commands>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|Balíček|Identifikátor GUID, který identifikuje VSPackage, která poskytuje příkazy.<br /><br /> Například balíček = "guidVsPackage1Pkg".|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Menus – element](../extensibility/menus-element.md)|Definuje všechny nabídky, které implementuje VSPackage.|  
|[Groups – element](../extensibility/groups-element.md)|Obsahuje položky, které definují příkaz skupiny ve VSPackage.|  
|[Buttons – element](../extensibility/buttons-element.md)|Tlačítko prvky skupiny.|  
|[Bitmaps – element](../extensibility/bitmaps-element.md)|Prvky skupiny rastrového obrázku.|  
|[Combos – element](../extensibility/combos-element.md)|Prvky pole se seznamem skupin.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[CommandTable – element](../extensibility/commandtable-element.md)|Definuje všechny elementy, které představují příkazy, které poskytuje VSPackage k prostředí IDE. Možné prvky jsou položky nabídky, nabídek, panely nástrojů a pole se seznamem.|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak používat [příkazy Element](../extensibility/commands-element.md).  
  
```  
<Commands package="guidMyPackage">  
    <Menus>  
      <Menu Condition="'%(DEBUG)' != 'true'"   
        guid="cmdSetGuidMyProductCommands" id="menuIDMainMenu"   
        priority="0x0000" type="Menu">  
        <Annotation>  
          <Documentation>this is an annotation</Documentation>  
          <AppInfo>  
            <CustomData>  
              <CustomSubElement>Some data</CustomSubElement>  
            </CustomData>  
          </AppInfo>  
        </Annotation>  
        <CommandFlag>AlwaysCreate</CommandFlag>  
        <Strings>  
          <ButtonText>MainMenu</ButtonText>  
        </Strings>  
      </Menu>  
  </Menus>  
<Commands>  
```  
  
## <a name="see-also"></a>Viz také  
 [Jak přidat VSPackages prvky uživatelského rozhraní](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Příkazy, nabídky a panely nástrojů](../extensibility/internals/commands-menus-and-toolbars.md)