---
title: Šablony projektů a souborů
ms.date: 01/02/2018
ms.topic: conceptual
helpviewer_keywords:
- templates [Visual Studio], project
- templates [Visual Studio], item
- item templates [Visual Studio]
- project templates [Visual Studio]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 079c1ee65ba5691504752e0f7d4e1f46ad06c525
ms.sourcegitcommit: 5af29226aef0a3b4a506b69a08a97cfd21049521
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/20/2019
ms.locfileid: "58268501"
---
# <a name="project-and-item-templates"></a>Šablony projektů a položek

Šablony projektů a položek poskytují opakovaně použitelný, která uživatelům umožňují základní kód a strukturu, který můžete přizpůsobit pro vlastní účely.

## <a name="visual-studio-templates"></a>šablony sady Visual Studio

Několik předdefinovaných projektů a šablon položek je nainstalováno pomocí sady Visual Studio. Tyto šablony, jako **webová aplikace ASP.NET** a **knihovny tříd** šablony, je možné vybírat při vytváření nového projektu. Šablony položek, jako jsou soubory kódu, souborů XML, HTML stránky a šablony stylů, se zobrazí v **přidat novou položku** okna.

Tyto šablony představují výchozí bod pro uživatele a začněte vytvářet projekty nebo rozšířit projekty stávající. Šablony projektů poskytují soubory, které jsou požadovány pro konkrétní typ projektu, zahrnují standardní odkazy na sestavení a nastavují výchozí vlastnosti projektu a možnosti kompilátoru. Šablony položek mohou být v rozsahu od jednoho prázdný soubor, který má určitá příponu souboru, do více souborů se zdrojovým kódem se zakázaným inzerováním kódem, informační soubory pro návrháře a vložené prostředky.

Můžete použít nainstalovaných šablon, vytvořit vlastní šablony, nebo stáhnout a použít šablonu vytvořenou komunitou. Další informace najdete v tématu [jak: Vytváření šablon projektu](../ide/how-to-create-project-templates.md) a [jak: Tvorba šablon položek s](../ide/how-to-create-item-templates.md).

## <a name="contents-of-a-template"></a>Obsah šablony

Všechny šablony projektů a položek, zda je nainstalován se sadou Visual Studio nebo vytvořené vámi, pracovat na stejných principech a mají podobný obsah. Všechny šablony obsahují následující položky:

- Soubory, které mají být vytvořeny při použití této šablony. Tyto soubory zahrnují soubory zdrojového kódu, vložené prostředky, soubory projektu a tak dále.

::: moniker range="vs-2017"

- A *.vstemplate* soubor, který obsahuje metadata potřebná k vytvoření projektu nebo položky ze šablony a k zobrazení šablony v **nový projekt** a **přidat novou položku** systém Windows.

::: moniker-end

::: moniker range=">=vs-2019"

- A *.vstemplate* soubor, který obsahuje metadata potřebná k vytvoření projektu nebo položky z této šablony a zobrazení šablony na **vytvořte nový projekt** stránku nebo **přidat novou položku** okna.

::: moniker-end

   Další informace o *.vstemplate* soubory, naleznete v tématu [parametry šablony](../ide/template-parameters.md).

Když jsou tyto soubory zkomprimovány do *ZIP* soubor a uložte do správné složky, Visual Studio automaticky zobrazí na následujících místech:

::: moniker range="vs-2017"

- Šablony projektu se zobrazí v **nový projekt** okna.

::: moniker-end

::: moniker range=">=vs-2019"

- Šablony projektu se zobrazí na **vytvořte nový projekt** stránky.

::: moniker-end

- Položka šablony se zobrazí v **přidat novou položku** okna.

Další informace o adresářích pro šablony najdete v tématu [jak: Hledání a organizace šablon](../ide/how-to-locate-and-organize-project-and-item-templates.md).

## <a name="see-also"></a>Viz také:

- [Postupy: Vytváření šablon projektu](../ide/how-to-create-project-templates.md)
- [Postupy: Tvorba šablon položek](../ide/how-to-create-item-templates.md)
- [Parametry šablony](../ide/template-parameters.md)
- [Přizpůsobení šablony](../ide/customizing-project-and-item-templates.md)
- [Balíčky NuGet ve šablony sady Visual Studio](/nuget/visual-studio-extensibility/visual-studio-templates)