---
title: "Položka funkce | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: msbuild, Item functions
ms.assetid: 5e6df3cc-2db8-4cbd-8fdd-3ffd03ac0876
caps.latest.revision: "28"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: e3b99f769b92ddd9f44f2a95b122e5e388954aef
ms.sourcegitcommit: f36eb7f989efbdbed0d0a087afea8ffe27d8ca15
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/14/2017
---
# <a name="item-functions"></a>Funkce položek
Od verze nástroje MSBuild 4.0, kód v úlohy a cíle můžete volat funkce položek se získat informace o položkách v projektu. Tyto funkce zjednodušit získávání Distinct() položky a je rychlejší než ve smyčce přes položky.  
  
## <a name="string-item-functions"></a>Řetězec funkce položek  
 Řetězec metody a vlastnosti, můžete použít v rozhraní .NET Framework pracovat na jakoukoli hodnotu položky. Pro <xref:System.String> metody, zadejte název metody. Pro <xref:System.String> vlastnosti, zadejte název vlastnosti za "get_".  
  
 Pro položky, které mají více řetězců řetězec metody nebo vlastnosti běží na každý řetězec.  
  
 Následující příklad ukazuje, jak používat tyto funkce položek řetězec.  
  
```xml  
<ItemGroup>  
    <theItem Include="andromeda;tadpole;cartwheel" />  
</ItemGroup>  
  
<Target Name = "go">  
    <Message Text="IndexOf  @(theItem->IndexOf('r'))" />  
    <Message Text="Replace  @(theItem->Replace('tadpole', 'pinwheel'))" />  
    <Message Text="Length   @(theItem->get_Length())" />  
    <Message Text="Chars    @(theItem->get_Chars(2))" />  
</Target>  
  
  <!--  
  Output:  
    IndexOf  3;-1;2  
    Replace  andromeda;pinwheel;cartwheel  
    Length   9;7;9  
    Chars    d;d;r  
  -->  
```  
  
## <a name="intrinsic-item-functions"></a>Funkce vnitřní položek  
 Následující tabulka uvádí vnitřní funkce, které jsou dostupné pro položky.  
  
|Funkce|Příklad|Popis|  
|--------------|-------------|-----------------|  
|`Count`|`@(MyItem->Count())`|Vrátí počet položek.|  
|`DirectoryName`|`@(MyItem->DirectoryName())`|Vrátí ekvivalent `Path.DirectoryName` pro každou položku.|  
|`Distinct`|`@(MyItem->Distinct())`|Vrátí položky, které mají odlišné `Include` hodnoty. Metadata se ignoruje. Porovnání nejsou rozlišována malá a velká písmena.|  
|`DistinctWithCase`|`@(MyItem->DistinctWithCase())`|Vrátí položky, které mají odlišné `itemspec` hodnoty. Metadata se ignoruje. Porovnání se rozlišují malá a velká písmena.|  
|`Reverse`|`@(MyItem->Reverse())`|Vrátí položky v obráceném pořadí.|  
|`AnyHaveMetadataValue`|`@(MyItem->AnyHaveMetadataValue("MetadataName", "MetadataValue"))`|Vrátí `boolean` k označení, zda má libovolnou položku daná metadata název a hodnotu. Porovnání nejsou rozlišována malá a velká písmena.|  
|`ClearMetadata`|`@(MyItem->ClearMetadata())`|Vrátí položky s jeho metadata vymazán. Pouze `itemspec` se uchovávají.|  
|`HasMetadata`|`@(MyItem->HasMetadata("MetadataName"))`|Vrátí položky, které mají název daná metadata. Porovnání nejsou rozlišována malá a velká písmena.|  
|`Metadata`|`@(MyItem->Metadata("MetadataName"))`|Vrátí hodnoty metadat, které mají název metadat.|  
|`WithMetadataValue`|`@(MyItem->WithMetadataValue("MetadataName", "MetadataValue"))`|Vrátí položky, které mají daná metadata název a hodnotu. Porovnání nejsou rozlišována malá a velká písmena.|  
  
 Následující příklad ukazuje, jak používat funkce vnitřní položek.  
  
```xml  
<ItemGroup>  
    <TheItem Include="first">  
        <Plant>geranium</Plant>  
    </TheItem>  
    <TheItem Include="second">  
        <Plant>algae</Plant>  
    </TheItem>  
    <TheItem Include="third">  
        <Plant>geranium</Plant>  
    </TheItem>  
</ItemGroup>  
  
<Target Name="go">  
    <Message Text="MetaData:    @(TheItem->Metadata('Plant'))" />  
    <Message Text="HasMetadata: @(theItem->HasMetadata('Plant'))" />  
    <Message Text="WithMetadataValue: @(TheItem->WithMetadataValue('Plant', 'geranium'))" />  
    <Message Text=" " />  
    <Message Text="Count:   @(theItem->Count())" />  
    <Message Text="Reverse: @(theItem->Reverse())" />  
</Target>  
  
  <!--   
  Output:  
    MetaData:    geranium;algae;geranium  
    HasMetadata: first;second;third  
    WithMetadataValue: first;third  
  
    Count:   3  
    Reverse: third;second;first  
  -->  
```  
  
## <a name="see-also"></a>Viz také  
 [Položky](../msbuild/msbuild-items.md)
