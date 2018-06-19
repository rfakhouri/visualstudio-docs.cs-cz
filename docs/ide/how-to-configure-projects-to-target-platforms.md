---
title: 'Postupy: Konfigurace projektů pro cílové platformy'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-compile
ms.topic: conceptual
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
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8f5f5552cb87f1c8b4501930f23765143a9e9399
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31946686"
---
# <a name="how-to-configure-projects-to-target-platforms"></a>Postupy: Konfigurace projektů pro cílové platformy

Visual Studio umožňuje nastavení vaší aplikací pro různé platformy, včetně 64bitové platformy. Další informace o podporovaných 64bitové platformě v sadě Visual Studio najdete v tématu [64bitové aplikace](http://msdn.microsoft.com/Library/fd4026bc-2c3d-4b27-86dc-ec5e96018181).

## <a name="target-platforms-with-the-configuration-manager"></a>Cílové platformy pomocí nástroje Configuration Manager

**Nástroje Configuration Manager** poskytuje způsob, jak můžete rychle přidat nová platforma k cíli s projektem. Pokud vyberete jednu z platformy zahrnutá v sadě Visual Studio, jsou vlastnosti pro svůj projekt upravit tak, aby sestavení projektu pro vybranou platformu.

### <a name="to-configure-a-project-to-target-a-64-bit-platform"></a>Ke konfiguraci projektu pro platformu 64-bit

1.  Na řádku nabídek zvolte **sestavení** > **nástroje Configuration Manager**.

2.  V **platforma Active řešení** seznam, vyberte 64bitovou platformu pro řešení k cíli a potom zvolte **Zavřít** tlačítko.

    1.  Pokud platformy, na které chcete, aby se nezobrazí v **platforma Active řešení** vyberte **nový**.

         **Nová platforma řešení** zobrazí se dialogové okno.

    2.  V **zadejte nebo vyberte nové platformě** vyberte **x64**.

        > [!NOTE]
        >  Pokud poskytnete konfiguraci nový název, možná budete muset změnit nastavení v **Návrhář projektu** pro správné platformu.

    3.  Pokud chcete tato nastavení zkopírovat z aktuální konfigurace platformy, zvolte jej a potom zvolte **OK** tlačítko.

Jsou aktualizovány vlastnosti pro všechny projekty, které používají 64bitovou platformu, a další sestavení projektu se optimalizovaný pro 64bitové platformy.

## <a name="target-platforms-in-the-project-designer"></a>Cílové platformy v Návrháři projektu

**Návrhář projektu** také poskytuje způsob, jak různé platformy s projektem. Pokud výběrem jedné z platforem zahrnuty v seznamu **nová platforma řešení** dialogové okno pro vaše řešení nefunguje, můžete vytvořit vlastní konfigurace název a upravit nastavení v **Návrhář projektu**  pro správné platformu.

Provedení tohoto úkolu se liší podle programovací jazyk, který používáte. V následujících tématech pro další informace:

-   Pro [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projekty, najdete v části [/Platform (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/platform).

-   Pro [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] projekty, najdete v části [stránka sestavení, Návrhář projektu (C#)](../ide/reference/build-page-project-designer-csharp.md).

-   Pro [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] projekty, najdete v části [/CLR (kompilace Common Language Runtime)](/cpp/build/reference/clr-common-language-runtime-compilation).

## <a name="see-also"></a>Viz také

- [Principy platforem sestavení](../ide/understanding-build-platforms.md)
- [/ Platform (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/platform-compiler-option)
- [64bitové aplikace](http://msdn.microsoft.com/Library/fd4026bc-2c3d-4b27-86dc-ec5e96018181)
- [Visual Studio IDE 64-Bit support](../ide/visual-studio-ide-64-bit-support.md)
