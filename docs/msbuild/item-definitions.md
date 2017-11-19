---
title: "Položka definice | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: msbuild, item definitions
ms.assetid: 8e3dc223-f9e5-4974-aa0e-5dc7967419cb
caps.latest.revision: "21"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: b2cf0713a38187f27bfddd46b0ad32b592d397a0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="item-definitions"></a>Definice položek
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]2.0 umožňuje statické deklaraci položky v souborech projektu pomocí [ItemGroup](../msbuild/itemgroup-element-msbuild.md) element. Však metadat lze přidat pouze na úrovni položek, i když je stejný pro všechny položky metadat. Počínaje [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 3.5, element projektu s názvem [ItemDefinitionGroup](../msbuild/itemdefinitiongroup-element-msbuild.md) překonává toto omezení. *ItemDefinitionGroup* umožňuje definovat sadu definice položek, které přidat výchozí hodnoty metadata pro všechny položky v typu s názvem položky.  
  
 *ItemDefinitionGroup* prvek se zobrazuje ihned po [projektu](../msbuild/project-element-msbuild.md) element souboru projektu. Definice položek poskytují následující funkce:  
  
-   Můžete definovat výchozí globální metadata pro položky mimo cíl. To znamená platí stejné metadata pro všechny položky zadaného typu.  
  
-   Typy položek může mít několik definic. Po přidání dalších metadat specifikace typu, specifikace poslední přednost. \(Metadaty dodržuje stejné pořadí import jako postupujte podle vlastnosti.\)  
  
-   Může být metadata sčítání. Například CDefines hodnoty počítají podmíněná, v závislosti na vlastnosti, která jsou nastavena. Například `MT;STD_CALL;DEBUG;UNICODE`.  
  
-   Metadata nelze odebrat.  
  
-   Podmínky lze použít k řízení zahrnutí metadat.  
  
## <a name="item-metadata-default-values"></a>Položka metadat výchozí hodnoty  
 Metadata položky, která je definována v ItemDefinitionGroup je právě deklaraci výchozí metadat. Metadata nelze použít, dokud nedefinujete položku, která se používá ItemGroup tak, aby obsahovala hodnoty metadat.  
  
> [!NOTE]
>  V mnoha příkladech v tomto tématu se zobrazí ItemDefinitionGroup element ale jeho odpovídající definice ItemGroup je vynechán pro přehlednost.  
  
 Metadata explicitně definované v ItemGroup má přednost před metadata v ItemDefinitionGroup. Metadata v ItemDefinitionGroup platí pouze pro nedefinované metadata v ItemGroup. Příklad:  
  
```xml  
<ItemDefinitionGroup>  
    <i>  
        <m>m1</m>  
        <n>n1</n>  
    </i>        
</ItemDefinitionGroup>  
<ItemGroup>  
    <i Include="a">  
        <o>o1</o>  
        <n>n2</n>  
    </i>  
</ItemGroup>  
```  
  
 V tomto příkladu je výchozí metadata "m" použít na položku "i", protože metadata "m" nejsou výslovně definované položkou "i". Výchozí metadata "n" však není použita na položku "i", protože metadata "n" je již definována položka "i".  
  
> [!NOTE]
>  Názvy – Element XML a parametru se rozlišují\-citlivé. Položky metadat a položku\/názvy vlastností nejsou případu\-citlivé. Proto ItemDefinitionGroup položky, které mají názvy, které se liší pouze v případě zacházeno jako stejné ItemGroup.  
  
## <a name="value-sources"></a>Hodnota zdroje  
 Hodnoty pro metadata, která je definována v ItemDefinitionGroup mohou pocházet z mnoha různých zdrojů, následujícím způsobem:  
  
-   PropertyGroup – vlastnost  
  
-   Položku z ItemDefinitionGroup  
  
-   Transformace položku na položku ItemDefinitionGroup  
  
-   Proměnné prostředí  
  
-   Globální vlastnost \(z příkazového řádku MSBuild.exe\)  
  
-   Rezervované vlastnosti  
  
-   Dobře\-známé metadata u položky z ItemDefinitionGroup  
  
-   Oddíl CDATA \< \! \[CDATA\[zde není analyzovat\]\]\>  
  
> [!NOTE]
>  Metadata položky z ItemGroup není užitečné v deklaraci ItemDefinitionGroup metadata, protože ItemDefinitionGroup elementy se zpracují dříve, než ItemGroup elementy.  
  
## <a name="additive-and-multiple-definitions"></a>Doplňkové a několik definic  
 Při přidávání definic nebo použití více ItemDefinitionGroups, mějte na paměti následující:  
  
-   Specifikace dalších metadat se přidá do typu.  
  
-   Specifikace poslední změny mají přednost.  
  
 Pokud máte více ItemDefinitionGroups, každý následné specifikace přidá jeho metadata k definici předchozí. Příklad:  
  
```xml  
<ItemDefinitionGroup>  
    <i>  
        <m>m1</m>  
        <n>n1</n>  
    </i>  
</ItemDefinitionGroup>  
<ItemDefinitionGroup>  
    <i>  
        <o>o1</o>  
    </i>  
</ItemDefinitionGroup>  
```  
  
 V tomto příkladu se přidá metadata "o" a "m", "n".  
  
 Kromě toho lze také přidat hodnoty předem definovaná metadata. Příklad:  
  
```xml  
<ItemDefinitionGroup>  
    <i>  
        <m>m1</m>  
    </i>  
</ItemDefinitionGroup>  
<ItemDefinitionGroup>  
    <i>  
        <m>%(m);m2</m>  
    </i>  
</ItemDefinitionGroup>    
```  
  
 V tomto příkladu dříve definovanou hodnotu pro metadata "m" \(m1\) se přidá na novou hodnotu \(m2\)tak, aby konečná hodnota je "m1; m2".  
  
> [!NOTE]
>  Tato situace může také nastat ve stejné ItemDefinitionGroup.  
  
 Při přepsání dříve definovaném metadat specifikace poslední přednost. V následujícím příkladu přejde konečná hodnota metadat "m" z "m1" na "m1a".  
  
```xml  
<ItemDefinitionGroup>  
    <i>  
        <m>m1</m>  
    </i>  
</ItemDefinitionGroup>  
<ItemDefinitionGroup>  
    <i>  
        <m>m1a</m>  
    </i>  
</ItemDefinitionGroup>    
```  
  
## <a name="using-conditions-in-an-itemdefinitiongroup"></a>Pomocí podmínek v ItemDefinitionGroup  
 Podmínky v ItemDefinitionGroup můžete použít k řízení zahrnutí metadat. Příklad:  
  
```xml  
<ItemDefinitionGroup Condition="'$(Configuration)'=='Debug'">  
    <i>  
        <m>m1</m>  
    </i>  
</ItemDefinitionGroup>  
```  
  
 V takovém případě je součástí výchozí metadata "m1" na položku "i", pouze pokud je hodnota vlastnosti "Konfigurace" "Debug".  
  
> [!NOTE]
>  V podmínky jsou podporovány pouze odkazy na místních metadat.  
  
 Odkazy na metadata definované v předchozích ItemDefinitionGroup jsou místní vzhledem k položce, ne definice skupiny. To znamená, rozsah odkazy jsou položky\-konkrétní. Příklad:  
  
```xml  
<ItemDefinitionGroup>  
    <test>  
        <yes>1</yes>  
    </test>  
    <i> 
        <m>m0</m>
        <m Condition="'%(test.yes)'=='1'">m1</m>  
    </i>  
</ItemDefinitionGroup>  
  
```  
  
V tomto příkladu položka "i" odkazuje na položku "test" v jeho stavu. Tato podmínka nebude nikdy hodnotu true, protože MSBuild interpretuje odkaz na další položku metadat v ItemDefinitionGroup jako prázdný řetězec. Proto by byl nastaven "m" na "m0."
 
```xml 
  <ItemDefinitionGroup>
    <i>
      <m>m0</m>
      <yes>1</yes>
      <m Condition="'%(i.yes)'=='1'">m1</m>
    </i>
  </ItemDefinitionGroup>

```

V předchozím příkladu "m" se nastavuje na hodnotu "m1" jako odkazy na stav položky "i" je hodnota metadat pro položku "Ano". 
  
## <a name="overriding-and-deleting-metadata"></a>Přepsání a odstraňování metadat  
 Metadata definovaná v elementu ItemDefinitionGroup je možné přepsat v předchozím prvku ItemDefinitionGroup nastavení na hodnotu metadata prázdné. Položka metadat také efektivně odstraníte jeho nastavení na prázdnou hodnotu. Příklad:  
  
```xml  
<ItemDefinitionGroup>  
    <i>  
        <m>m1</m>  
    </i>  
</ItemDefinitionGroup>  
<ItemDefinitionGroup>  
    <i>  
        <m></m>  
    </i>  
</ItemDefinitionGroup>  
```  
  
 Položka "i" stále obsahuje metadata "m", ale její hodnota je prázdná.  
  
## <a name="scope-of-metadata"></a>Obor metadat  
 ItemDefinitionGroups mít globální obor na určené a globální vlastnosti, kde jsou definovány. Výchozí definice metadat v ItemDefinitionGroup může být sám sebou\-referenční. Následující příklad používá metadaty odkaz:  
  
```xml  
<ItemDefinitionGroup>  
    <i>  
        <m>m1</m>  
        <m>%(m);m2</m>  
    </i>  
</ItemDefinitionGroup>  
```  
  
 Odkaz kvalifikovaný metadata lze také použít:  
  
```xml  
<ItemDefinitionGroup>  
    <i>  
      <m>m1</m>  
      <m>%(i.m);m2</m>  
    </i>  
</ItemDefinitionGroup>  
```  
  
 Ale toto není platná:  
  
```xml  
<ItemDefinitionGroup>  
    <i>  
        <m>m1</m>  
        <m>@(x)</m>  
    </i>  
</ItemDefinitionGroup>  
```  
  
 Počínaje [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 3.5, ItemGroups můžete také být sám sebou\-referenční. Příklad:  
  
```xml  
<ItemGroup>  
    <item Include="a">  
        <m>m1</m>  
        <m>%(m);m2</m>  
    </item>  
</ItemGroup>  
```  
  
## <a name="see-also"></a>Viz také  
 [Dávkování](../msbuild/msbuild-batching.md)
