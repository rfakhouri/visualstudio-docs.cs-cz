---
title: Tlačítko Element | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- Buttons element (VSCT XML schema)
- VSCT XML schema elements, Buttons
ms.assetid: 96dccf51-2b00-4700-9d28-924b34c21ecd
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 58f63968ed02f49b0ccfa4dda24f684fed339bc4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54760762"
---
# <a name="button-element"></a>Button – element
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Definuje element, který může uživatel zasahovat. Tlačítka mohou být různých typů: Tlačítka, nabídky a SplitDropDown.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Button guid="guidMyCommandSet" id="MyCommand" priority="0x102" type="button">  
  <Parent>... </Parent>  
  <Icon>... </Icon>  
  <CommandFlag>... </CommandFlag>  
  <Strings>... </Strings>  
</Button>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|identifikátor GUID|Povinný parametr. Identifikátor GUID identifikátoru GUID a ID příkazu.|  
|id|Povinný parametr. ID identifikátoru GUID a ID příkazu.|  
|priorita|Volitelné. Číselná hodnota, která určuje prioritu.|  
|– typ|Volitelné. Výčtová hodnota, která určuje typ tlačítka.<br /><br /> Pokud není zadaný, použije tlačítko.<br /><br /> Tlačítko<br /> Standardní příkaz, který se zobrazí na panely nástrojů (obvykle jako ikony tlačítka), nabídky a kontextové nabídky.<br /><br /> MenuButton<br /> Položka nabídky, která není provedení příkazu, ale vytváří jiné nabídky.<br /><br /> SplitDropDown<br /> Ovládací prvky, jako jsou tlačítka Zpět a znovu na standardním panelu nástrojů v aplikaci Microsoft Word.|  
|Podmínka|Volitelné. Zobrazit [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Parent – element](../extensibility/parent-element.md)|Volitelné. Nadřazený prvek tlačítko.|  
|[Icon – element](../extensibility/icon-element.md)|Volitelné. Ikona přidružený k tlačítku.|  
|[Command Flag – element](../extensibility/command-flag-element.md)|Povinný parametr. Platné hodnoty CommandFlag pro tlačítka jsou následujícím způsobem.<br /><br /> -AllowParams<br /><br /> -CommandWellOnly<br /><br /> -DefaultDisabled<br /><br /> -DefaultInvisible<br /><br /> - DontCache<br /><br /> -DynamicItemStart<br /><br /> -DynamicVisibility<br /><br /> - FixMenuController<br /><br /> - IconAndText<br /><br /> -NoButtonCustomize<br /><br /> -NoCustomize<br /><br /> -NoKeyCustomize<br /><br /> - NoShowOnMenuController<br /><br /> -Pict<br /><br /> -PostExec<br /><br /> - ProfferedCmd<br /><br /> -RouteToDocs<br /><br /> - TextCascadeUseBtn<br /><br /> -TextMenuUseButton<br /><br /> -TextChanges<br /><br /> -TextChangesButton<br /><br /> - TextContextUseButton<br /><br /> - TextMenuCtrlUseMenu<br /><br /> -TextMenuUseButton<br /><br /> -Typu TextOnly|  
|[Strings – element](../extensibility/strings-element.md)|Povinný parametr. Podřízené [ButtonText – Element](../extensibility/buttontext-element.md) musí být definovaný.|  
|Poznámka|Volitelný komentář.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Buttons – element](../extensibility/buttons-element.md)|Seskupí elementy tlačítko.|  
  
## <a name="example"></a>Příklad  
 Následující příklad definuje v souboru .vsct tlačítko.  
   
 ```xml
<Button guid="guidMenuTextCmdSet" id="cmdidMyCommand" priority="0x0100" type="Button">
    <Parent guid="guidMenuTextCmdSet" id="MyMenuGroup" />
    <Icon guid="guidImages" id="bmpPic1" />
    <CommandFlag>TextChanges</CommandFlag>
    <Strings>
          <CommandName>cmdidMyCommand</CommandName>
          <ButtonText>My Command name</ButtonText>
    </Strings>
</Button>
 ```

## <a name="see-also"></a>Viz také  
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
