---
title: "Vytváření šablon projektu pro Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 01/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ExportTemplateWizard
helpviewer_keywords:
- project templates [Visual Studio], creating
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0da7a7979b4fed6f58cdda6f1eafa55517e4df9b
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/05/2018
---
# <a name="how-to-create-project-templates"></a>Postupy: vytváření šablon projektu

Toto téma ukazuje, jak vytvořit šablonu pomocí **Průvodce exportem šablony**, které balíčky šablony do souboru ZIP.

## <a name="to-create-a-user-project-template-by-using-the-export-template-wizard"></a>Vytvoření šablony projektu uživatele pomocí průvodce Exportovat šablonu

1. Vytvořte projekt.

    > [!NOTE]
    > Používejte pouze platný identifikátor – znaky pojmenování projektu, který bude sloužit jako zdroj pro šablonu. Chyby při kompilaci může dojít v projektech, které jsou vytvořené ze šablony. Další informace o platný identifikátor – znaky najdete v tématu [deklarované názvy elementu (Visual Basic)](/dotnet/visual-basic/programming-guide/language-features/declared-elements/declared-element-names) nebo [identifikátory (C++)](/cpp/cpp/identifiers-cpp). Alternativně můžete použít [parametry šablony](../ide/template-parameters.md) použít "bezpečnou" názvy tříd a obory názvů.

1. Upravte projekt, dokud je připraven k exportu jako šablona. Například můžete chtít upravit soubory kódu k označení, kde by měl proběhnout nahrazení parametru. V tématu [postupy: nahrazení parametrů v šabloně](../ide/how-to-substitute-parameters-in-a-template.md).

1. Na **projektu** nabídce zvolte **exportovat šablonu...** .

   **Průvodce exportem šablony** otevře.

1. Na **výběr typu šablony** vyberte **šablona projektu**. Vyberte projekt, který chcete exportovat do šablony a potom vyberte **Další**.

1. Na **vyberte možnosti šablony** stránky, zadejte název a volitelný popis ikonu a zobrazení náhledu obrázku pro šablonu. Tyto položky se zobrazí v **nový projekt** dialogové okno. Zvolte **Dokončit**.

  Projekt je exportovali do souboru ZIP a umístit do zadané výstupní umístění a, importu do sady Visual Studio.

>[!NOTE]
> Najít vaše šablony v **nový projekt** dialogové okno, rozbalte seznam **nainstalovaná** a potom rozbalte kategorii, která odpovídá `ProjectType` element v souboru .vstemplate. Například .vstemplate soubor, který obsahuje `<ProjectType>CSharp</ProjectType>` se zobrazí pod **nainstalovaná** > **Visual C#**, ve výchozím nastavení. Šablony můžete uspořádat do podadresáři typ projektu pouze po vytvoření složky v tomto adresáři a umístění souboru .zip vaše šablony v ní. Další informace najdete v tématu [postupy: hledání a organizace šablon](../ide/how-to-locate-and-organize-project-and-item-templates.md).

## <a name="other-ways-to-create-project-templates"></a>Další způsoby vytváření šablon projektu

Šablony projektů můžete vytvořit ručně shromažďování souborů, které tvoří projektu do složky a pak vytvořit .vstemplate soubor XML s metadaty vhodné. Další informace najdete v tématu [postupy: ruční vytvoření webových šablon](../ide/how-to-manually-create-web-templates.md).

Pokud máte sadu Visual Studio SDK nainstalovat, můžete zabalit dokončenou šablonu do souboru VSIX pro nasazení pomocí **projektu VSIX** šablony. Další informace najdete v tématu [Začínáme s šablona projektu VSIX](../extensibility/getting-started-with-the-vsix-project-template.md).

## <a name="see-also"></a>Viz také

[Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)  
[Postupy: Vytváření šablon položek](../ide/how-to-create-item-templates.md)  
[Začínáme s šablona projektu VSIX](../extensibility/getting-started-with-the-vsix-project-template.md)
