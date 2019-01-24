---
title: Metadata jako zdroj | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
dev_langs:
- CSharp
helpviewer_keywords:
- Go To Definition command
- Code Definition window, viewing metadata as source
- metadata as source [C#]
ms.assetid: 4945a07f-b3be-4f05-a587-fc29058aa8fa
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 8d1a4d269b0b7e1afb151bea5bbd97d5ab770d00
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54791051"
---
# <a name="metadata-as-source"></a>Metadata jako zdroj
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Metadata jako zdroj umožňuje zobrazit metadata, která se zobrazí jako zdrojový kód C# ve vyrovnávací paměti jen pro čtení. To umožňuje zobrazení deklarací typů a členů (bez implementace). Metadata jako zdroj můžete zobrazit spuštěním **přejít k definici** příkaz pro typy nebo členy, jejíž zdrojový kód není k dispozici v projektu nebo řešení.  
  
> [!NOTE]
>  Při pokusu o spuštění **přejít k definici** příkaz pro typy nebo členy, které jsou označeny jako vnitřní, integrované vývojové prostředí (IDE) nezobrazuje jejich metadata jako zdroj, bez ohledu na to, jestli se odkazující sestavení je přítele či nikoli.  
  
 Můžete zobrazit metadata jako zdroj v obou editoru kódu nebo **definice kódu** okna.  
  
## <a name="viewing-metadata-as-source-in-the-code-editor"></a>Zobrazení metadat jako zdroje v editoru kódu  
 Při spuštění **přejít k definici** příkaz pro některou položku, jejíž zdrojový kód je k dispozici, dokument s kartami, který obsahuje zobrazení metadat danou položku, zobrazí jako zdroj, se zobrazí v editoru kódu. Název typu, následovaný **[z metadat]**, se zobrazí na kartě dokumentu.  
  
 Například pokud spustíte **přejít k definici** příkazu <xref:System.Console>, metadata pro <xref:System.Console> se zobrazí v editoru kódu, jako zdrojový kód C#, která se podobá jeho deklaraci, ale bez implementace.  
  
 ![Metadata jako zdroj](../csharp-ide/media/metadatasource.png "MetadataSource")  
  
## <a name="viewing-metadata-as-source-in-the-code-definition-window"></a>Zobrazení metadat jako zdroje v okně Definice kódu  
 Když **definice kódu** okna je aktivní nebo viditelné, automaticky spustí rozhraní IDE **přejít k definici** příkaz pro položky pod kurzor v editoru kódu a pro položky, které jsou vybrány v  **Zobrazení tříd** nebo **Prohlížeč objektů**. Pokud zdrojový kód není k dispozici pro danou položku, rozhraní IDE zobrazí položky metadat jako zdroje v **definice kódu** okna.  
  
 Například, pokud umístěte kurzor dovnitř slovo <xref:System.Console> v editoru kódu, metadata pro <xref:System.Console> se zobrazí jako zdroj v **definice kódu** okna. Vypadá podobně jako zdroj <xref:System.Console> deklaraci, ale bez implementace.  
  
 Pokud chcete zobrazit položky, které se zobrazí v deklaraci **definice kódu** okna, klikněte pravým tlačítkem na položku a klikněte na tlačítko **přejít k definici**.