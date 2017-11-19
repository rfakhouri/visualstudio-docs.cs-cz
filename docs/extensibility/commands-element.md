---
title: "Příkazy Element | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Commands
helpviewer_keywords:
- Commands element (VSCT XML schema)
- VSCT XML schema elements, Commands
ms.assetid: 47cf16a5-d78b-452e-86f6-b5893856dddf
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 61d7f67eda9bdd1d215586a75ed01c1089ccf7fc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
|[Element nabídky](../extensibility/menus-element.md)|Definuje všechny nabídky, které implementuje VSPackage.|  
|[Element skupiny](../extensibility/groups-element.md)|Obsahuje položky, které definují příkaz skupiny ve VSPackage.|  
|[Element tlačítka](../extensibility/buttons-element.md)|Tlačítko prvky skupiny.|  
|[Rastrové obrázky – Element](../extensibility/bitmaps-element.md)|Prvky skupiny rastrového obrázku.|  
|[Element kláves](../extensibility/combos-element.md)|Prvky pole se seznamem skupin.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[CommandTable Element](../extensibility/commandtable-element.md)|Definuje všechny elementy, které představují příkazy, které poskytuje VSPackage k prostředí IDE. Možné prvky jsou položky nabídky, nabídek, panely nástrojů a pole se seznamem.|  
  
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
 [Příkazy, nabídek a panelů nástrojů](../extensibility/internals/commands-menus-and-toolbars.md)