---
title: "Postupy: Konfigurace projektů pro cílové platformy | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project settings [Visual Studio], targeting platforms
- platforms, targeting specific CPUs
- project properties [Visual Studio], targeting platforms
- projects [Visual Studio], targeting platforms
- 64-bit [Visual Studio]
- 64-bit programming [Visual Studio]
- CPUs, targeting specific
- 64-bit applications [Visual Studio]
ms.assetid: 845302fc-273d-4f81-820a-7296ce91bd76
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 22838f561793845c9b44e57631c46773b094c98b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-configure-projects-to-target-platforms"></a>Postupy: Konfigurace projektů pro cílové platformy
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]Umožňuje nastavit aplikací pro různé platformy, včetně 64bitové platformy. Další informace na 64bitové platformě podpoře v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], najdete v části [64bitové aplikace](http://msdn.microsoft.com/Library/fd4026bc-2c3d-4b27-86dc-ec5e96018181).  
  
## <a name="targeting-platforms-with-the-configuration-manager"></a>Cílení na platformy pomocí nástroje Configuration Manager  
 **Nástroje Configuration Manager** poskytuje způsob, jak můžete rychle přidat nová platforma k cíli s projektem. Pokud vyberete jednu z platformy součástí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], úpravě vlastností pro svůj projekt k sestavení projektu pro vybranou platformu.  
  
#### <a name="to-configure-a-project-to-target-a-64-bit-platform"></a>Ke konfiguraci projektu pro platformu 64-bit  
  
1.  Na řádku nabídek zvolte **sestavení**, **nástroje Configuration Manager**.  
  
2.  V **platforma Active řešení** seznam, vyberte 64bitovou platformu pro řešení k cíli a potom zvolte **Zavřít** tlačítko.  
  
    1.  Pokud platformy, na které chcete, aby se nezobrazí v **platforma Active řešení** vyberte **nový**.  
  
         **Nová platforma řešení** zobrazí se dialogové okno.  
  
    2.  V **zadejte nebo vyberte nové platformě** vyberte **x64**.  
  
        > [!NOTE]
        >  Pokud poskytnete konfiguraci nový název, možná budete muset změnit nastavení v **Návrhář projektu** pro správné platformu.  
  
    3.  Pokud chcete tato nastavení zkopírovat z aktuální konfigurace platformy, zvolte jej a potom zvolte **OK** tlačítko.  
  
 Jsou aktualizovány vlastnosti pro všechny projekty, které používají 64bitovou platformu, a další sestavení projektu se optimalizovaný pro 64bitové platformy.  
  
## <a name="targeting-platforms-in-the-project-designer"></a>Cílení na platformy v Návrháři projektu  
 Návrhář projektu také poskytuje způsob, jak různé platformy s projektem. Pokud výběrem jedné z platforem zahrnuty v seznamu **nová platforma řešení** dialogové okno pro vaše řešení nefunguje, můžete vytvořit vlastní konfigurace název a upravit nastavení v **Návrhář projektu**  pro správné platformu.  
  
 Provedení tohoto úkolu se liší podle programovací jazyk, který používáte. V následujících tématech pro další informace:  
  
-   Pro [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projekty, najdete v části [/Platform (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/platform).  
  
-   Pro [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] projekty, najdete v části [stránka sestavení, Návrhář projektu (C#)](../ide/reference/build-page-project-designer-csharp.md).  
  
-   Pro [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] projekty, najdete v části [/CLR (kompilace Common Language Runtime)](/cpp/build/reference/clr-common-language-runtime-compilation).  
  
## <a name="see-also"></a>Viz také  
 [Principy platforem sestavení](../ide/understanding-build-platforms.md)   
 [/ Platform (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/platform-compiler-option)   
 [64bitové aplikace](http://msdn.microsoft.com/Library/fd4026bc-2c3d-4b27-86dc-ec5e96018181)   
 [Podpora 64bitových technologií sady Visual Studio IDE](../ide/visual-studio-ide-64-bit-support.md)