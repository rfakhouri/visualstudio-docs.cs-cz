---
title: Tlačítko Element | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Buttons element (VSCT XML schema)
- VSCT XML schema elements, Buttons
ms.assetid: 96dccf51-2b00-4700-9d28-924b34c21ecd
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e10b4f8749aa7e42a7fb95afb31d98907e45d05f
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66321289"
---
# <a name="button-element"></a>Element přepínače
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
| – typ|Volitelné. Výčtová hodnota, která určuje typ tlačítka.<br /><br /> Pokud není zadaný, použije tlačítko.<br /><br /> Tlačítko<br /> Standardní příkaz, který se zobrazí na panely nástrojů (obvykle jako ikony tlačítka), nabídky a kontextové nabídky.<br /><br /> MenuButton<br /> Položka nabídky, která není provedení příkazu, ale vytváří jiné nabídky.<br /><br /> SplitDropDown<br /> Ovládací prvky, jako jsou tlačítka Zpět a znovu na standardním panelu nástrojů v aplikaci Microsoft Word.|
|Podmínka|Volitelné. Zobrazit [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|

### <a name="child-elements"></a>Podřízené elementy

|Prvek|Popis|
|-------------|-----------------|
|[Nadřazený element](../extensibility/parent-element.md)|Volitelné. Nadřazený prvek tlačítko.|
|[Icon – element](../extensibility/icon-element.md)|Volitelné. Ikona přidružený k tlačítku.|
|[Command flag – element](../extensibility/command-flag-element.md)|Povinný parametr. Platné hodnoty CommandFlag pro tlačítka jsou následujícím způsobem.<br /><br /> -AllowParams<br /><br /> -CommandWellOnly<br /><br /> -DefaultDisabled<br /><br /> -DefaultInvisible<br /><br /> - DontCache<br /><br /> -DynamicItemStart<br /><br /> -DynamicVisibility<br /><br /> - FixMenuController<br /><br /> - IconAndText<br /><br /> -NoButtonCustomize<br /><br /> -NoCustomize<br /><br /> -NoKeyCustomize<br /><br /> - NoShowOnMenuController<br /><br /> -Pict<br /><br /> -PostExec<br /><br /> - ProfferedCmd<br /><br /> -RouteToDocs<br /><br /> - TextCascadeUseBtn<br /><br /> -TextMenuUseButton<br /><br /> -TextChanges<br /><br /> -TextChangesButton<br /><br /> - TextContextUseButton<br /><br /> - TextMenuCtrlUseMenu<br /><br /> -TextMenuUseButton<br /><br /> -Typu TextOnly|
|[Strings – element](../extensibility/strings-element.md)|Povinný parametr. Podřízené [ButtonText – element](../extensibility/buttontext-element.md) musí být definovaný.|
|Poznámka|Volitelný komentář.|

### <a name="parent-elements"></a>Nadřazené prvky

|Prvek|Popis|
|-------------|-----------------|
|[Buttons – element](../extensibility/buttons-element.md)|Seskupí elementy tlačítko.|

## <a name="example"></a>Příklad
 Následující příklad definuje tlačítka v *.vsct* souboru.

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

## <a name="see-also"></a>Viz také:
- [Soubory tabulky (.vsct) příkaz pro Visual Studio](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)