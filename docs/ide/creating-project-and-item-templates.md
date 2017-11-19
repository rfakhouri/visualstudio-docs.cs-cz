---
title: "Vytváření šablon projektů a položek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- templates [Visual Studio], projects
- item templates, about item templates
- templates [Visual Studio], item
- Visual Studio templates, item
- Visual Studio templates, about templates
- project templates [Visual Studio], about project templates
- Visual Studio templates, project
- templates [Visual Studio], about templates
ms.assetid: a6ce501a-699b-4e3e-ade8-c81895645c20
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7d95781c2c5c4370e09c13b382016b015ec1a0d5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="creating-project-and-item-templates"></a>Vytváření šablon projektů a položek
Šablony projektů a položek aplikace [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] poskytují opakovaně použitelný kód, který uživatelům dává základní kód a strukturu, což mohou využít pro vlastní účely.  
  
## <a name="visual-studio-templates"></a>Šablony aplikace Visual Studio  
 Několik předdefinovaných šablon projektů a položek je nainstalováno již po instalaci aplikace [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] a [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] aplikace Windows Forms a knihovny tříd šablon, které jsou k dispozici v **nový projekt** dialogové okno jsou příklady šablon projektů. Jsou k dispozici v nainstalované šablony položek **přidat novou položku** dialogové okno pole a zahrnout položek, jako jsou soubory kódu, soubory XML, stránky HTML a stylů.  
  
 Tyto šablony představují výchozí bod pro uživatele, aby mohli začít projekty vytvářet nebo rozšířit projekty stávající. Šablony projektů poskytují soubory, které jsou požadovány pro konkrétní typ projektu, zahrnují standardní odkazy na sestavení a nastavují výchozí vlastnosti projektu a možnosti kompilátoru. Šablony položek mohou mít různou strukturu od jednoho prázdného souboru, který má správnou příponu, až k vícesouborové položce, která například obsahuje zdrojové soubory se základním kódem, informační soubory pro návrháře a vložené prostředky.  
  
 Kromě nainstalovaných šablon v **nový projekt** a **přidat novou položku** dialogových oken, můžete vytvořit vlastní šablony nebo stažení a použití šablony vytvořené komunitou. Další informace najdete v tématu [postupy: vytvoření šablony projektů](../ide/how-to-create-project-templates.md) a [postupy: vytváření šablon položek](../ide/how-to-create-item-templates.md).  
  
## <a name="contents-of-a-template"></a>Obsah šablony  
 Všechny šablony projektů a položek, ať už instalované spolu s aplikací [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nebo vytvořené vámi, fungují na stejných principech a mají podobný obsah. Všechny šablony obsahují následující položky:  
  
-   Soubory, které mají být vytvořeny při použití této šablony. To zahrnuje zdrojové soubory, vložené prostředky, soubory projektu a tak dále.  
  
-   Jeden soubor .vstemplate. Tento soubor obsahuje metadata, která poskytuje [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] informace, musí se zobrazit šablonu v **nový projekt** a **přidat novou položku** dialogových oken a vytvoření projektu nebo položky z Šablona. Další informace o soubory .vstemplate najdete v tématu [parametry šablony](../ide/template-parameters.md).  
  
 Pokud tyto soubory jsou komprimované do souboru ZIP a umístí ve správné složce, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] je automaticky zobrazí. Šablony projektu se zobrazí v **šablony** části **nový projekt** dialogových oken a šablon položek se zobrazí v **přidat novou položku** dialogová okna. Další informace o složkách šablony najdete v tématu [postupy: vyhledání a uspořádání šablony](../ide/how-to-locate-and-organize-project-and-item-templates.md).  
  
## <a name="starter-kits"></a>startovní sady  
 Startovní sady jsou zdokonalené šablony, které lze veřejně sdílet s ostatními členy komunity. Startovní sada obsahuje ukázky kódu s kompilací, dokumentaci a další prostředky, které mají za úkol pomoci uživatelům naučit se nové nástroje a programovací techniky, aby mohli tvořit užitečné a opravdové aplikace. Základní obsah a postupy pro startovní sady jsou stejné jako pro šablony. Další informace najdete v tématu [postupy: vytváření Startovních sad](../ide/how-to-create-starter-kits.md).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytváření šablon projektu](../ide/how-to-create-project-templates.md)   
 [Postupy: vytváření šablon položek](../ide/how-to-create-item-templates.md)   
 [Parametry šablony](../ide/template-parameters.md)   
 [Přizpůsobení šablon](../ide/customizing-project-and-item-templates.md)   
 [Postupy: vytváření Startovních sad](../ide/how-to-create-starter-kits.md)