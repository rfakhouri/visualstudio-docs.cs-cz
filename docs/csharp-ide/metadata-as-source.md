---
title: Metadata jako zdroj | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: CSharp
helpviewer_keywords:
- Go To Definition command
- Code Definition window, viewing metadata as source
- metadata as source [C#]
ms.assetid: 4945a07f-b3be-4f05-a587-fc29058aa8fa
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 29b783e20925b3eaa4a7b0956fdcfdbcab06a328
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="metadata-as-source"></a>Metadata jako zdroj
Metadata jako zdroj umožňuje zobrazit metadata, která se zobrazí jako zdrojový kód C# do vyrovnávací paměti jen pro čtení. To umožňuje zobrazení deklarace typů a členů (bez implementace). Metadata jako zdroj můžete zobrazit spuštěním **přejít k definici** příkazu pro typy nebo členy, jejichž zdrojový kód není k dispozici z projekt nebo řešení.  
  
> [!NOTE]
>  Při pokusu o spuštění **přejít k definici** příkaz pro typy nebo členy, které jsou označené jako vnitřní integrované vývojové prostředí (IDE) nejsou zobrazeny jejich metadata jako zdroj, bez ohledu na to, jestli odkazující sestavení je přítele či nikoli.  
  
 Můžete zobrazit metadata jako zdroj v buď editoru kódu nebo **definice kódu** okno.  
  
## <a name="viewing-metadata-as-source-in-the-code-editor"></a>Zobrazení metadat jako zdroje v editoru kódu  
 Při spuštění **přejít k definici** příkaz položky jejichž zdrojový kód je k dispozici, dokumentů s kartami, která obsahuje zobrazení této položky metadat, zobrazí jako zdroj, zobrazí se v editoru kódu. Název typu následovaný **[z metadat]**, se zobrazí na kartě dokumentu.  
  
 Například pokud spustíte **přejít k definici** příkazu pro <xref:System.Console>, metadata pro <xref:System.Console> se zobrazí v editoru kódu, jako zdrojový kód C# podobná jeho deklaraci, ale bez implementace.  
  
 ![Metadata jako zdroj](../csharp-ide/media/metadatasource.png "MetadataSource")  
  
## <a name="viewing-metadata-as-source-in-the-code-definition-window"></a>Zobrazení metadat jako zdroje v okně Definice kódu  
 Když **definice kódu** automaticky provede rozhraní IDE, je aktivní nebo viditelné **přejít k definici** příkazu pro položky v rámci kurzoru v editoru kódu a pro položky, které jsou vybrány v  **Třídy zobrazení** nebo **objektu prohlížeče**. Pokud zdrojový kód není k dispozici pro tuto položku, rozhraní IDE zobrazuje jako zdroj v metadata položky **definice kódu** okno.  
  
 Například, pokud umístěte kurzor uvnitř slova <xref:System.Console> v editoru kódu, metadata pro <xref:System.Console> se zobrazí jako zdroj v **definice kódu** okno. Zdroj se podobá <xref:System.Console> deklarace, ale bez implementace.  
  
 Pokud chcete zobrazit prohlášení o položku, která se zobrazí v **definice kódu** okna, klikněte pravým tlačítkem položku a klikněte na tlačítko **přejít k definici**.