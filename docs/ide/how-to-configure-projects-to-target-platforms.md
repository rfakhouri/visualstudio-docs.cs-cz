---
title: 'Postupy: Konfigurace projektů pro cílové platformy'
ms.date: 11/04/2016
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
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: faef9f55a88385953a121574f761193cc8c11ea9
ms.sourcegitcommit: 59e5758036223ee866f3de5e3c0ab2b6dbae97b6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/23/2019
ms.locfileid: "68416831"
---
# <a name="how-to-configure-projects-to-target-platforms"></a>Postupy: Konfigurace projektů pro cílové platformy

Visual Studio umožňuje nastavení aplikací na různých platformách, včetně 64bitových platforem. Další informace o podpoře platforem 64-bit v sadě Visual Studio najdete v tématu [64bitové aplikace](/dotnet/framework/64-bit-apps).

## <a name="target-platforms-with-the-configuration-manager"></a>Cílové platformy s Configuration Manager

**Configuration Manager** poskytuje způsob, jak rychle přidat novou platformu pro cílení na váš projekt. Pokud vyberete jednu z platforem, které jsou součástí sady Visual Studio, vlastnosti projektu jsou upraveny pro sestavení projektu pro vybranou platformu.

### <a name="to-configure-a-project-to-target-a-64-bit-platform"></a>Konfigurace projektu pro cílení na 64 platformu

1. Na panelu nabídek vyberte možnost **sestavit** > **Configuration Manager**.

2. V seznamu **Aktivní platforma řešení** zvolte 64 platformu pro cílové řešení a pak klikněte na tlačítko **Zavřít** .

    1. Pokud se požadovaná platforma nezobrazí v seznamu **Aktivní platforma řešení** , vyberte možnost **nové**.

         Zobrazí se dialogové okno **Nová platforma řešení** .

    2. V rozevíracím seznamu **Typ vyberte Nová platforma** a zvolte možnost **x64**.

        > [!NOTE]
        > Pokud vaší konfiguraci přiřadíte nový název, může být nutné upravit nastavení v **Návrháři projektu** , aby se zacíleno na správnou platformu.

    3. Pokud chcete zkopírovat nastavení z aktuální konfigurace platformy, vyberte ji a pak klikněte na tlačítko **OK** .

Vlastnosti pro všechny projekty, které cílí na 64, jsou aktualizovány a další sestavení projektu bude optimalizováno pro 64-bitové platformy.

## <a name="target-platforms-in-the-project-designer"></a>Cílové platformy v Návrháři projektu

**Návrhář projektu** také poskytuje způsob, jak cílit na různé platformy s vaším projektem. Pokud výběr jedné z platforem zahrnutých v seznamu v dialogovém okně **Nová platforma řešení** nefunguje pro vaše řešení, můžete vytvořit vlastní název konfigurace a upravit nastavení v **Návrháři projektu** , abyste mohli cílit na správnou platformu. .

Provádění tohoto úkolu se liší v závislosti na programovacím jazyku, který používáte. Další informace najdete na následujících odkazech:

- Pro [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projekty naleznete v tématu [/Platform (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/platform).

- Pro [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] projekty, viz [Stránka sestavení, Návrhář projektu (C#)](../ide/reference/build-page-project-designer-csharp.md).

- Pro [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] projekty naleznete v tématu [/CLR (Common Language Runtime Compilation)](/cpp/build/reference/clr-common-language-runtime-compilation).

## <a name="see-also"></a>Viz také:

- [Principy platforem sestavení](../ide/understanding-build-platforms.md)
- [/Platform (C# možnosti kompilátoru)](/dotnet/csharp/language-reference/compiler-options/platform-compiler-option)
- [64 – bitové aplikace](/dotnet/framework/64-bit-apps)
- [Visual Studio IDE 64 – Podpora bitových procesorů](../ide/visual-studio-ide-64-bit-support.md)
