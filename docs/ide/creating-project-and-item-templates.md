---
title: "Šablony sady Visual Studio pro projekty a soubory | Microsoft Docs"
ms.custom: 
ms.date: 01/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- templates [Visual Studio], project
- templates [Visual Studio], item
- item templates [Visual Studio]
- project templates [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3959b01fdfc0ff77bdd5a3ffa0c96366b9da87d7
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/05/2018
---
# <a name="project-and-item-templates"></a>Šablony projektů a položek

Šablony projektů a položek poskytují opakovaně použitelné zástupných procedur, která uživatelům umožňují některé základní kódu a struktura, která můžete přizpůsobit pro vlastní účely.

## <a name="visual-studio-templates"></a>šablony sady Visual Studio

Několik předdefinovaných projektů a šablon položek je nainstalováno pomocí sady Visual Studio. Například Visual Basic a C# **aplikace pro Windows Forms** a **knihovny tříd** šablony, které jsou zobrazeny v **nový projekt** dialogové okno jsou šablony projektů. Šablony položek se zobrazují v **přidat novou položku** dialogové okno pole a zahrnout položek, jako jsou soubory kódu, soubory XML, stránky HTML a stylů.

Tyto šablony představují výchozí bod pro uživatele zahájíte vytváření projektů nebo rozšířit existující projekty. Šablony projektů poskytují soubory, které jsou požadovány pro konkrétní typ projektu, zahrnují standardní odkazy na sestavení a nastavují výchozí vlastnosti projektu a možnosti kompilátoru. Šablony položek může pohybovat složitost z jedné prázdný soubor, který má určitá příponu souboru, položku více soubory, které obsahuje, například, soubory zdrojového kódu, které mají se zakázaným inzerováním kód, informace o návrháři souborů a vložené prostředky.

Kromě nainstalovaných šablon v **nový projekt** a **přidat novou položku** dialogových oken, můžete vytvořit vlastní šablony, nebo stažení a použití šablony vytvořené komunitou. Další informace najdete v tématu [postupy: vytváření šablon projektu](../ide/how-to-create-project-templates.md) a [postupy: vytváření šablon položek](../ide/how-to-create-item-templates.md).

## <a name="contents-of-a-template"></a>Obsah šablony

Všechny šablony projektů a položek, ať už nainstalované s Visual Studio nebo vytvořené vámi, funkce pomocí stejné zásady a mají podobný obsah. Všechny šablony obsahují následující položky:

- Soubory, které mají být vytvořeny při použití této šablony. To zahrnuje zdrojové soubory, vložené prostředky, soubory projektu a tak dále.

- Jeden soubor .vstemplate. Tento soubor obsahuje metadata, která poskytuje informace potřebné k zobrazení šablony **nový projekt** a **přidat novou položku** dialogových oken a vytvořte projekt nebo položku ze šablony. Další informace o soubory .vstemplate najdete v tématu [parametry šablony](../ide/template-parameters.md).

Když tyto soubory jsou komprimované do souboru ZIP a put ve správné složce, Visual Studio automaticky zobrazí na těchto místech:

- Šablony projektu se zobrazí v **nový projekt** dialogové okno.

- Šablony položek se zobrazí v **přidat novou položku** dialogové okno.

Další informace o složkách šablony najdete v tématu [postupy: hledání a organizace šablon](../ide/how-to-locate-and-organize-project-and-item-templates.md).

## <a name="starter-kits"></a>startovní sady

Startovní sady jsou zdokonalené šablony, které lze veřejně sdílet s ostatními členy komunity. Startovní sada obsahuje ukázky kódu s kompilací, dokumentaci a další prostředky, které mají za úkol pomoci uživatelům naučit se nové nástroje a programovací techniky, aby mohli tvořit užitečné a opravdové aplikace. Základní obsah a postupy pro startovní sady jsou stejné jako pro šablony. Další informace najdete v tématu [postupy: vytváření Startovních sad](../ide/how-to-create-starter-kits.md).

## <a name="see-also"></a>Viz také

[Postupy: vytváření šablon projektu](../ide/how-to-create-project-templates.md)  
[Postupy: vytváření šablon položek](../ide/how-to-create-item-templates.md)  
[Parametry šablony](../ide/template-parameters.md)  
[Přizpůsobení šablon](../ide/customizing-project-and-item-templates.md)  
[Balíčky NuGet ve šablony sady Visual Studio](/nuget/visual-studio-extensibility/visual-studio-templates)