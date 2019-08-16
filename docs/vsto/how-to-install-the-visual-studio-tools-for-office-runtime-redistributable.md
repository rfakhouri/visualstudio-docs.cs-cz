---
title: 'Postupy: Nainstalovat Visual Studio Tools for Office distribuovatelné za běhu'
titleSuffix: ''
ms.custom: seodec18
ms.date: 08/14/2019
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
ms.openlocfilehash: 5d9bb53fbdc3d6766dab47c654f0a43ad902b2f3
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69551835"
---
# <a name="how-to-install-the-visual-studio-tools-for-office-runtime-redistributable"></a>Postupy: Nainstalovat Visual Studio Tools for Office distribuovatelné za běhu
  Nástroje Visual Studio 2010 Tools for Office runtime musí být nainstalované na každém počítači, na kterém běží řešení vytvořená pomocí nástrojů systém Microsoft Office Developer Tools v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Modul runtime se nainstaluje automaticky při instalaci [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]nástroje a systém Microsoft Office. Další informace najdete v tématu [scénáře instalace modulu runtime Visual Studio Tools for Office](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md).

[!include[Add-ins note](includes/addinsnote.md)]

 Možná budete muset postupovat podle pokynů k ruční instalaci v následujících situacích:

- Musíte nainstalovat [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] na server. Například chcete použít <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třídu ke správě řešení na úrovni dokumentu na serveru.

- Je potřeba nainstalovat modul runtime na počítač, který už má nainstalované všechny ostatní předpoklady pro řešení Office.

    > [!NOTE]
    > Abyste mohli nainstalovat .NET Framework a, [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]musíte být správcem vývojového počítače.

## <a name="to-install-the-visual-studio-tools-for-office-runtime"></a>Instalace modulu runtime Visual Studio Tools for Office

1. [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] Nainstalujte nebo novější.

    - Pokud si chcete [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]stáhnout, přečtěte si článek [Microsoft .NET Framework 4 (Webová instalační služba)](http://go.microsoft.com/fwlink/?LinkId=178957).

    - Pokud si chcete [!INCLUDE[net_client_v40_long](../vsto/includes/net-client-v40-long-md.md)]stáhnout, přečtěte si článek [Profil klienta Microsoft .NET Framework 4 (Webová instalační služba)](http://go.microsoft.com/fwlink/?LinkId=178958).

    - Informace o stažení [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]najdete v tématu [Microsoft .NET Framework 4,5](http://www.microsoft.com/download/details.aspx?id=30653).

2. Spusťte *vstor_redist. exe* a nainstalujte [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].

     Tyto instalační soubory si můžete stáhnout z [nástroje Visual Studio 2010 Tools for Office runtime](http://go.microsoft.com/fwlink/?LinkId=140384). Předpoklady pro [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] odpovídající požadavky pro .NET Framework.

     [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Zahrnuje jazykové sady. Pokud je vaše instalace systému Windows nastavená na jiný jazyk než angličtinu, můžete zobrazit zprávy za běhu ve stejném jazyce, který používáte pro Windows. Podobně platí, že pokud koncoví [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] uživatelé nainstalují a pak spouštějí vaše řešení na instalacích systému Windows, které jsou nastaveny na jiný jazyk než angličtinu, budou se zprávy za běhu zobrazovat ve stejném jazyce jako Windows. V některých případech možná budete potřebovat další jazykové sady. Můžete například potřebovat další jazykové sady, pokud vaše kopie systému Windows používá více než jedno nastavení jazyka nebo pokud jste již nainstalovali [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]sadu, jste přepnuli na jiný jazyk. Jazykové sady můžete najít v [Microsoft Visual Studio 2010 nástrojích pro systém Microsoft Office systému (verze 4,0 Runtime) pro jazykovou sadu](http://go.microsoft.com/fwlink/?LinkId=140386).

## <a name="see-also"></a>Viz také:
- [Začínáme &#40;s vývojem pro Office v sadě Visual Studio&#41;](../vsto/getting-started-office-development-in-visual-studio.md)
- [Konfigurace počítače pro vývoj řešení pro systém Office](../vsto/configuring-a-computer-to-develop-office-solutions.md)
- [Postupy: Konfigurace počítače pro vývoj řešení pro systém Office](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md)
- [Postupy: Nainstalovat primární spolupracující sestavení pro Office](../vsto/how-to-install-office-primary-interop-assemblies.md)
- [Správa dokumentů na serveru pomocí třídy ServerDocument](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)
- [Nasazení řešení pro systém Office](../vsto/deploying-an-office-solution.md)
