---
title: "Bitmap – Element | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSCT XML schema elements, Bitmaps
- Bitmaps element (VSCT XML schema)
ms.assetid: edcd7891-f4e7-416d-809d-5e2eed9f17e4
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 223342709dbe97fe38fb7a495ce482ae70e1c807
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="bitmap-element"></a>Bitmap – Element
Definuje rastrový obrázek. Bitmapy je načten z prostředku nebo ze souboru.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Bitmap guid="guidImages" href="images\MyImage.bmp" usedList="bmp1, bmp2, bmp3" />  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|Identifikátor GUID|Požadováno. Identifikátor GUID identifikátor GUID nebo ID příkazu.<br /><br /> Atribut guid rastrového obrázku není přidružený žádné VSPackage nebo jiné skupiny pro příkaz.  To by měl být jedinečný v definici rastrového obrázku a by se neměla používat za žádným jiným účelem.|  
|resID|ID identifikátor GUID nebo ID příkazu. Je požadována resID nebo atribut href.<br /><br /> Atribut resID je ID prostředku celé číslo, které určuje pruhu rastrový obrázek, který se má načíst během tabulky příkaz sloučení.  Při načítání tabulky příkaz bitmap určeného ID prostředku budou načteny z prostředku stejném modulu.|  
|usedList|Vyžaduje se, zda je přítomen atribut resID. Vybere dostupných imagí v pruhu rastrového obrázku.|  
|href|Cesta k bitové mapy. Je požadována resID nebo atribut href.<br /><br /> Cesta zahrnutí je hledán souboru uvedené bitové kopie, která je integrována do výsledný binární soubor.  Při slučování tabulky příkaz je zkopírovat bitovou kopii a není potřeba žádná další prostředků vyhledávání nebo zatížení.  Pokud atribut usedList není zadán, jsou k dispozici všechny Image v pruh. **Poznámka:** bitové kopie může být zadána v některém z formátů, které zahrnují GIF, BMP a .png.  Starší verze kompilátoru nepodporuje 32bitové rastrové obrázky, které měl alfa informace pro částečné průhlednost. Alternativní řešení pro tyto verze se má používat formát PNG.|  
|Podmínka|Volitelné. V tématu [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Rastrové obrázky – Element](../extensibility/bitmaps-element.md)|Prvky skupiny rastrového obrázku.|  
  
## <a name="example"></a>Příklad  
  
```  
<Bitmap guid="guidWidgetIcons" href="WidgetToolbarIcons_32.bmp" />  
<Bitmap guid="guidWidgetIcons2" resID="IDBMP_WIDGETICONS"  
  usedList="1, 2, 3, 4"/>  
```  
  
## <a name="see-also"></a>Viz také  
 [Visual Studio příkaz tabulky (. Soubory Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)