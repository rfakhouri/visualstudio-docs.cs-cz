---
title: Symboly Element | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Symbols element (VSCT XML schema)
- VSCT XML schema elements, Symbols
ms.assetid: 1cda43d8-42a5-4b1b-a3c8-cf0401c3202f
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4ef5b215e18163b10c8002affc959bd80b586cf0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="symbols-element"></a>Element symboly
Definuje identifikátory, které jsou používány jiné VSCT elementy a identifikátory GUID. Pro nespravovaného kódu, tyto informace obvykle pochází z soubory hlaviček, které jsou určené [Extern Element](../extensibility/extern-element.md). Spravovaný kód používá podřízených elementů symboly elementu, který chcete definovat tyto informace.  
  
 Pokud vytvoříte soubor .vsct z existujícího souboru .cto, vygeneruje se symboly jako podřízené objekty daného elementu symboly. Další informace najdete v tématu [postupy: vytvoření. Soubor Vsct z existující. Soubor technického ředitele](../extensibility/internals/how-to-create-a-dot-vsct-file.md#how-to-create-a-dot-vsct-file-from-an-existing-dot-cto-file).  
  
 Element symboly Nezaměňovat s [definovat Element](../extensibility/define-element.md), která definuje dvojice název hodnota pro použití preprocesor.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Symbols>  
  <GuidSymbol>... </GuidSymbol>  
  <GuidSymbol>... </GuidSymbol>  
</Symbols>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|Žádné||  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|GuidSymbol|Definuje symbol identifikátor GUID. GuidSymbol má dva povinné atributy: název a hodnotu. Název je název symbolu a hodnota je hodnota identifikátoru GUID jako řetězec.<br /><br /> Příklad:\<GuidSymbol name = "guidVsPackage1Pkg" value = "{c5f54698-101a-4846-84d3-dc748f9cd848}" / >|  
|IDSymbol|Definuje symbol. IDSymbol má dva povinné atributy: název a hodnotu. Název je název symbolu a hodnota je hodnota symbolu jako řetězec.<br /><br /> Příklad:\<IDSymbol name = "MyMenuGroup" value = "0x1020" / >|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[CommandTable Element](../extensibility/commandtable-element.md)|Kořenový element .vsct souboru.|  
  
## <a name="example"></a>Příklad  
  
```  
<Symbols>  
  <GuidSymbol name="guidVsPackage1Pkg" value="{c5f54698-101a-4846-84d3-dc748f9cd848}" />  
  <GuidSymbol name="guidVsPackage1CmdSet" value="{cb9dfd7f-2fcc-4a3e-aae8-f7fe30b1cfac}">  
    <IDSymbol name="MyMenuGroup" value="0x1020" />  
    <IDSymbol name="cmdidMyCommand" value="0x0100" />  
    <IDSymbol name="cmdidMyTool" value="0x0101" />  
  </GuidSymbol>  
</Symbols>  
```  
  
## <a name="see-also"></a>Viz také  
 [Visual Studio příkaz tabulky (. Soubory Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)