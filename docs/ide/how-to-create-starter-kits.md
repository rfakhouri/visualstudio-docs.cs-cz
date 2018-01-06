---
title: "Postupy: vytváření Startovních sad | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Starter Kits, creating
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d5a779c1c8779c6d7126b67da9e60326284221a6
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/05/2018
---
# <a name="how-to-create-starter-kits"></a>Postupy: Vytváření startovních sad

Startovní sady obsahuje kód pro dokončení aplikace a dokumentaci o tom, jak změnit nebo rozbalte aplikaci. Vytvoření Starter Kit je zásadně stejný jako při vytváření šablony Normální projektu, je jediným rozdílem že Starter Kit obsahuje soubory dokumentace, které jsou nastavené na otevřít, když na projekt podle Starter Kit je vytvořen.

## <a name="designing-and-developing-a-starter-kit"></a>Návrh a vývoj Startovní sady

Nejprve musíte určit typ Starter Kit, který chcete pro vývoj a definovat cílovou skupinu. V dalším kroku návrhu projektu a dokumentace, aby byly splněny cíle.

Pokud vytváříte ukázkové aplikace nebo modul plug-in:

- Vytvořte projekt, který vytvoří bez chyb.

- Přidejte kód šablony k provedení dalších úloh (volitelné).

- Připravte v dokumentaci.

Pokud vytváříte nástroj learning:

- Vytvořte projekt, který vytvoří bez chyb.

- Uspořádání prostředků, jako jsou fragmenty kódu a šablon položek.

- Připravte v dokumentaci.

## <a name="creating-a-template"></a>Vytvoření šablony

Po dokončení projektu a dokumentace, jste připraveni vytvořit šablona projektu pro Starter Kit. Tento proces je přesně stejný jako šablona projektu pro vytváření.

Následující témata obsahují informace o vytváření šablon:

- [Postupy: vytváření šablon projektu](../ide/how-to-create-project-templates.md) &ndash; vysvětluje, jak používat **Průvodce exportem šablony** k vytvoření šablony.
- [Postupy: aktualizace existujících šablon](../ide/how-to-update-existing-templates.md) &ndash; popisuje, jak upravit existující šablonu. Pomocí tohoto postupu upravte soubor .vstemplate přizpůsobit Starter Kit.

## <a name="see-also"></a>Viz také

[Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)  
[Přizpůsobení šablon](../ide/customizing-project-and-item-templates.md)  
[Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)