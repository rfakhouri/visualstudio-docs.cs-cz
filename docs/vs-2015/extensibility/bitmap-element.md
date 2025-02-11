---
title: Bitmap – Element | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- VSCT XML schema elements, Bitmaps
- Bitmaps element (VSCT XML schema)
ms.assetid: edcd7891-f4e7-416d-809d-5e2eed9f17e4
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: fc1fb57c7ec43421b211b29cfd6ab97b24a1864c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68184748"
---
# <a name="bitmap-element"></a>Bitmap – element
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Definuje rastrový obrázek. Rastrový obrázek je načten z prostředku nebo ze souboru.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Bitmap guid="guidImages" href="images\MyImage.bmp" usedList="bmp1, bmp2, bmp3" />  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|guid|Povinný parametr. Identifikátor GUID identifikátoru GUID a ID příkazu.<br /><br /> Atribut guid rastrového obrázku není přidružené žádné VSPackage nebo jiné skupiny příkazů.  Musí být jedinečné pro definici bitmapy a neměl by se používat k žádnému jinému účelu.|  
|resID|ID identifikátoru GUID a ID příkazu. Je požadován resID nebo atribut href.<br /><br /> Atribut resID je ID prostředku celé číslo, které určuje pruhu rastrový obrázek, který má být načten při slučování tabulky příkazů.  Při načítání tabulky příkazů rastrové obrázky určené ID prostředku se načtou z prostředku stejného modulu.|  
|usedList|Povinné, pokud je přítomen atribut resID. Vybere dostupných imagí v pruhu rastrového obrázku.|  
|href|Cesta k rastrového obrázku. Je požadován resID nebo atribut href.<br /><br /> Cesty zahrnutí se hledá soubor uvedeného obrázku, který je součástí výsledný binární soubor.  Během sloučení příkaz tabulky zkopírovat bitovou kopii a je potřeba žádné další prostředků vyhledávání nebo zatížení.  Pokud atribut usedList není k dispozici, jsou dostupné všechny Image v pruhu. **Poznámka:**  Image může být zadána v jednom z několika formátů, které zahrnují BMP, PNG nebo .gif.  Starší verze kompilátoru nepodporuje 32bitové rastrové obrázky, které měly alfa informace pro částečnou průhlednost. Alternativní řešení pro tyto verze má formát PNG.|  
|Podmínka|Volitelné. Zobrazit [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Bitmaps – element](../extensibility/bitmaps-element.md)|Seskupí elementy rastrového obrázku.|  
  
## <a name="example"></a>Příklad  
  
```  
<Bitmap guid="guidWidgetIcons" href="WidgetToolbarIcons_32.bmp" />  
<Bitmap guid="guidWidgetIcons2" resID="IDBMP_WIDGETICONS"  
  usedList="1, 2, 3, 4"/>  
```  
  
## <a name="see-also"></a>Viz také  
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
