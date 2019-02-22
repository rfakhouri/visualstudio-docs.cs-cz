---
title: 'Postupy: Nainstalovat Visual Studio Tools for Office runtime redistributable'
titleSuffix: ''
ms.custom: seodec18
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office runtime [Office development in Visual Studio]
- installing Office development tools in Visual Studio
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 3531fc79956b9c0f72d0dc5a333f1f9aedf5326d
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56609073"
---
# <a name="how-to-install-the-visual-studio-tools-for-office-runtime-redistributable"></a>Postupy: Nainstalovat Visual Studio Tools for Office runtime redistributable
  Visual Studio 2010 Tools for Office runtime musí být nainstalovaný na každém počítači, na kterém běží řešení, které jsou vytvořeny pomocí nástroje Microsoft Office developer tools v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Modul runtime se nainstaluje automaticky při instalaci [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]a Microsoft Office. Další informace najdete v tématu [Visual Studio Tools for Office runtime instalace scénáře](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md).

 Je třeba postupovat podle pokynů pro ruční instalaci níže v následujících situacích:

-   Je potřeba nainstalovat [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] na serveru. Například chcete použít <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třídy ke správě řešení na úrovni dokumentu na serveru.

-   Je potřeba nainstalovat modul runtime na počítači, který již má všechny další požadavky pro řešení Office nainstalována.

    > [!NOTE]
    >  Musíte být správce na vývojovém počítači, aby instalaci rozhraní .NET Framework a [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].

## <a name="to-install-the-visual-studio-tools-for-office-runtime"></a>Chcete-li nainstalovat Visual Studio Tools for Office runtime

1.  Nainstalujte [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější.

    -   Chcete-li stáhnout [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)], naleznete v tématu [rozhraní Microsoft .NET Framework 4 (Webová instalační služba)](http://go.microsoft.com/fwlink/?LinkId=178957).

    -   Chcete-li stáhnout [!INCLUDE[net_client_v40_long](../vsto/includes/net-client-v40-long-md.md)], naleznete v tématu [rozhraní Microsoft .NET Framework 4 Client Profile (Webová instalační služba)](http://go.microsoft.com/fwlink/?LinkId=178958).

    -   Chcete-li stáhnout [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)], naleznete v tématu [rozhraní Microsoft .NET Framework 4.5](http://www.microsoft.com/download/details.aspx?id=30653).

2.  Spustit *vstor_redist.exe* k instalaci [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].

     Můžete stáhnout z těchto instalačních souborů [Visual Studio 2010 Tools for Office runtime](http://go.microsoft.com/fwlink/?LinkId=140384). Požadavky pro [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] odpovídat požadavky pro rozhraní .NET Framework.

     [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Obsahuje jazykové sady. Pokud instalace systému Windows je nastavena na jiný jazyk než angličtinu, můžete zobrazit zprávy modulu runtime ve stejném jazyce, který používáte pro Windows. Podobně pokud si koncoví uživatelé nainstalují [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] a spusťte instalaci systému Windows, která jsou nastavena na jiný jazyk než angličtinu, zpráv modulu runtime se zobrazí ve stejném jazyce jako Windows vašich řešení. V některých případech můžete potřebovat další jazykové sady. Například může být nutné další jazykové sady, pokud vaše kopie systému Windows používá více než jedno nastavení jazyka nebo přepnout na jiný jazyk, poté, co jste již nainstalovali [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. Můžete najít jazykové sady v [Microsoft Visual Studio 2010 Tools pro Microsoft Office system (verze 4.0 modulu runtime) language pack](http://go.microsoft.com/fwlink/?LinkId=140386).

## <a name="see-also"></a>Viz také:
- [Začínáme &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/getting-started-office-development-in-visual-studio.md)
- [Konfigurace počítače pro vývoj řešení pro systém Office](../vsto/configuring-a-computer-to-develop-office-solutions.md)
- [Postupy: Konfigurace počítače pro vývoj řešení pro systém Office](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md)
- [Postupy: Instalace primárních sestavení vzájemné spolupráce Office](../vsto/how-to-install-office-primary-interop-assemblies.md)
- [Správa dokumentů na serveru s použitím třídy ServerDocument](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)
- [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)
