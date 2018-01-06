---
title: Projekt typu Essentials | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: project types [Visual Studio SDK]
ms.assetid: 09991589-2300-430e-b6a4-7f2b95fe676f
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 899d2758be1561d9b5fbda3280230333cc0ac8a3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="project-type-essentials"></a>Essentials typ projektu
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]obsahuje několik typů projekt pro jazyky, jako například [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] nebo [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)]. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]Umožňuje taky vytvořit vlastní typy projektů.  
  
 Pokud chcete přidat vlastní příkazy, editory nebo nástroj windows [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], můžete to provést bez vytvoření nového projektu typu. Další informace naleznete v následujících tématech:  
  
-   [Příkazy, nabídky a panely nástrojů](../../extensibility/internals/commands-menus-and-toolbars.md)  
  
-   [Editor a rozšíření služeb jazyka](../../extensibility/editor-and-language-service-extensions.md)  
  
-   [Rozšíření a přizpůsobení panelů nástrojů](../../extensibility/extending-and-customizing-tool-windows.md)  
  
 Podobně pokud chcete přizpůsobit chování zadaných [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] a [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] typy projektů, můžete provést tak pomocí podtypů projektu. Další informace najdete v tématu [projektu podtypů](../../extensibility/internals/project-subtypes.md).  
  
 Musíte vytvořit nový typ projektu pro projekty, které jsou založené na jazyce než [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] a [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] Pokud chcete zajistit podporu jeden nebo více následujících akcí:  
  
-   Sestavení  
  
-   Nasazení  
  
-   Více konfigurací  
  
-   Správa zdrojového kódu  
  
-   Ladění  
  
-   Položky projektu v Průzkumníku řešení  
  
-   **Otevřeného projektu** nebo **nový projekt** dialogových oken  
  
-   Vnoření projektu  
  
-   Další informace o možnostech typy projektů naleznete v následujících tématech:  
  
-   Typy projektů jsou objekty ve VSPackage, které implementují sadu rozhraní [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] očekává. Pokud používáte C# k vývoji typu projektu, třídy projektu spravované Framework balíček implementovat rozhraní potřebná pro vás a umožňují dědit tuto implementaci. Další informace najdete v tématu [použití rozhraní spravované balíček k implementaci typu projektu (C#)](../../extensibility/internals/using-the-managed-package-framework-to-implement-a-project-type-csharp.md).  
  
-   Pro vývojáře C++ třídy v knihovně HierUtil fungovat podobným způsobem. Další informace najdete v tématu [není v sestavení: pomocí HierUtil7 projektu třídy k implementaci typu projektu (C++)](http://msdn.microsoft.com/en-us/a5c16a09-94a2-46ef-87b5-35b815e2f346).  
  
-   Typy projektů může podporovat dat než typické zdrojové soubory sestavení do sestavení .exe nebo .dll. Například [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] databázové projekty obsahovat odkazy na skript a dotaz soubory uložené na disku a přidat příkazy **Průzkumníku řešení** spuštění skriptů a dotazy na databázi, ale projektů nepodporují sestavení chování. Další informace najdete v tématu [otevírání a ukládání položky projektu](../../extensibility/internals/opening-and-saving-project-items.md).  
  
-   Typ projektu nemá vůbec používat soubory. Typ projektu může například uložit všechna jeho data v databázi. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]typy projektů poskytuje úplnou kontrolu nad jak jejich zachování dat pro projekty a položky projektu. Další informace najdete v tématu [rozhodnutí o návrhu projektu typu](../../extensibility/internals/project-type-design-decisions.md).  
  
-   Musíte zadat typy projektů *vytváření projektu*, což je objekt, který vytvoří instanci projektu zadejte vždy, když [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] je vás vyzval k otevření nebo vytvořit projekt, který je založen na typu projektu. Další informace najdete v tématu [vytváření instancí podle pomocí projektu objekty pro vytváření projektů](../../extensibility/internals/creating-project-instances-by-using-project-factories.md).  
  
-   Typy projektů se musí zadat šablon projektů a položek projektů. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]používá šablony, když uživatelé vytvářet nové projekty a přidání nových položek do existující projekty. Další informace najdete v tématu [přidání projektů a šablon položek projektu](../../extensibility/internals/adding-project-and-project-item-templates.md).  
  
-   Typy projektů může podporovat víc konfigurací, jako je ladění a vydání. Uživatelé mohou změnit různé konfigurace projektu pomocí stránky vlastností, které zadáte. Další informace najdete v tématu [Správa možnosti konfigurace](../../extensibility/internals/managing-configuration-options.md).  
  
## <a name="see-also"></a>Viz také  
 [Nasazování typů projektů](../../extensibility/internals/deploying-project-types.md)