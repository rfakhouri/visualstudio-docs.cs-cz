---
title: 'Postupy: Připojení rozšíření spravovaného kódu k dokumentům'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- managed code extensions [Office development in Visual Studio], attaching
- documents [Office development in Visual Studio], managed code extensions
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: f56d51817491726e6011e965bfd6d68630bb0dbf
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63441806"
---
# <a name="how-to-attach-managed-code-extensions-to-documents"></a>Postupy: Připojení rozšíření spravovaného kódu k dokumentům
  Vytvoření vlastního nastavení sestavení můžete připojit k existující dokument aplikace Microsoft Office Word nebo sešit aplikace Microsoft Office Excel. Dokumentem nebo sešitem, může být v libovolném formátu souboru, který podporuje projekty Microsoft Office a nástroje pro vývoj v sadě Visual Studio. Další informace najdete v tématu [architektura přizpůsobení na úrovni dokumentu](../vsto/architecture-of-document-level-customizations.md).

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

 Přizpůsobení připojit k dokument aplikace Word nebo Excel, použijte <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A> metodu <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třídy. Vzhledem k tomu, <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třídy slouží ke spuštění v počítači, který nemá nainstalovanou sadu Microsoft Office, můžete použít tuto metodu v řešení, které přímo nesouvisejí s vývoj pro Microsoft Office (například konzole nebo aplikace Windows Forms).

> [!NOTE]
> Přizpůsobení se nepodaří načíst, pokud kód očekává, že ovládací prvky, které nemá zadaný dokument.

 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související video ukázku naleznete v tématu [postup: Připojení nebo odpojení sestavení VSTO z Wordového dokumentu? ](http://go.microsoft.com/fwlink/?LinkId=136782).

### <a name="to-attach-managed-code-extensions-to-a-document"></a>K připojení rozšíření spravovaného kódu do dokumentu

1. V projektu, který nevyžaduje, aby aplikace Microsoft Office, jako je například projekt aplikace Windows Forms a konzolové aplikace, přidejte odkaz na *Microsoft.VisualStudio.Tools.Applications.ServerDocument.dll* a  *Microsoft.VisualStudio.Tools.Applications.Runtime.dll* sestavení.

2. Přidejte následující **importy** nebo **pomocí** příkazy do horní části souboru kódu.

     [!code-csharp[Trin_VstcoreDeployment#4](../vsto/codesnippet/CSharp/Trin_VstcoreDeploymentCS/Program.cs#4)]
     [!code-vb[Trin_VstcoreDeployment#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreDeploymentVB/Program.vb#4)]

3. Zavolejte statickou <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A> metody.

     Následující příklad kódu používá <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A> přetížení. Toto přetížení má úplnou cestu k dokumentu a <xref:System.Uri> určující umístění manifestu nasazení pro přizpůsobení, kterou chcete připojit k tomuto dokumentu. Tento příklad předpokládá, že Wordového dokumentu s názvem **WordDocument1.docx** je na ploše a umístěný ve složce s názvem manifest nasazení **publikovat** , který je také v klientských počítačích.

     [!code-csharp[Trin_VstcoreDeployment#3](../vsto/codesnippet/CSharp/Trin_VstcoreDeploymentCS/Program.cs#3)]
     [!code-vb[Trin_VstcoreDeployment#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreDeploymentVB/Program.vb#3)]

4. Sestavte projekt a spusťte aplikaci v počítači, ve které chcete připojit vlastní nastavení. Počítač musí mít Visual Studio 2010 Tools for Office Runtime nainstalovaný.

## <a name="see-also"></a>Viz také:
- [Správa dokumentů na serveru s použitím třídy ServerDocument](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)
- [Postupy: Odebrání rozšíření spravovaného kódu z dokumentů](../vsto/how-to-remove-managed-code-extensions-from-documents.md)
- [Manifesty aplikace a nasazení v řešeních pro systém Office](../vsto/application-and-deployment-manifests-in-office-solutions.md)
