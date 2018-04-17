---
title: 'Postupy: odebrání rozšíření spravovaného kódu z dokumentů | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- managed code extensions [Office development in Visual Studio], removing
- documents [Office development in Visual Studio], managed code extensions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7a5e70db36c0cd1b99a670e13a353e15f7558e7e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-remove-managed-code-extensions-from-documents"></a>Postupy: Odebrání rozšíření spravovaného kódu z dokumentů
  Přizpůsobení sestavení prostřednictvím kódu programu můžete odebrat z dokumentu nebo sešitu, který je součástí přizpůsobení na úrovni dokumentu pro aplikace Microsoft Office Word nebo Microsoft Office Excel. Uživatelé pak můžete otevřít dokumenty a zobrazit obsah, ale nezobrazí se žádné vlastní uživatelské rozhraní (UI) přidáte k dokumentům, a váš kód nespustí.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Přizpůsobení sestavení můžete odebrat pomocí jedné z metod RemoveCustomization poskytované [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. Jakou metodu použijete, závisí na tom, jestli chcete odebrat přizpůsobení v době běhu (spuštěním kódu v přizpůsobení při slovo dokumentu nebo sešitu aplikace Excel je otevřený), nebo pokud chcete odebrat přizpůsobení z uzavřených dokumentu nebo dokumentu tento i s na serveru, který nemá nainstalovanou sadu Microsoft Office.  
  
 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související Videoukázka, najdete v části [provést jak I: připojit nebo odpojit sestavení VSTO z dokumentu aplikace Word?](http://go.microsoft.com/fwlink/?LinkId=136782).  
  
### <a name="to-remove-the-customization-assembly-at-run-time"></a>Chcete-li odebrat přizpůsobení sestavení za běhu  
  
1.  Ve vašem kódu přizpůsobení volání <xref:Microsoft.Office.Tools.Word.Document.RemoveCustomization%2A> – metoda (pro aplikaci Word) nebo <xref:Microsoft.Office.Tools.Excel.Workbook.RemoveCustomization%2A> – metoda (pro aplikaci Excel). Tato metoda by měla být volána pouze po přizpůsobení již není potřeba.  
  
     Kde volat tuto metodu v kódu závisí na tom, jak se používá vlastní. Například pokud zákazníci vaše přizpůsobení funkce používat, dokud jsou připravené k odeslání dokumentu pro ostatní klienty, které stačí přímo (není přizpůsobení) do dokumentu, můžete zadat některé uživatelského rozhraní, která volá RemoveCustomization, když zákazník klikne. Případně pokud vlastní naplní dokumentu s daty při prvním otevření, ale přizpůsobení neposkytuje žádné další funkce, které jsou dostupné přímo přes zákazníků, potom můžete volat RemoveCustomization co nejdříve vlastní dokončení inicializace dokumentu.  
  
### <a name="to-remove-the-customization-assembly-from-a-closed-document-or-a-document-on-a-server"></a>Přizpůsobení sestavení odebrání uzavřené dokument nebo dokumentu na serveru  
  
1.  V projektu, který nevyžaduje Microsoft Office, jako je například konzolovou aplikaci nebo v projektu Windows Forms přidejte odkaz na sestavení Microsoft.VisualStudio.Tools.Applications.ServerDocument.dll.  
  
2.  Přidejte následující **importy** nebo **pomocí** příkaz na začátek souboru kódu.  
  
     [!code-csharp[Trin_VstcoreDeployment#1](../vsto/codesnippet/CSharp/Trin_VstcoreDeploymentCS/Program.cs#1)]
     [!code-vb[Trin_VstcoreDeployment#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreDeploymentVB/Program.vb#1)]  
  
3.  Zavolejte statickou <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.RemoveCustomization%2A> metodu <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třídy a zadejte cestu dokumentu řešení pro parametr.  
  
     Následující příklad kódu předpokládá, že jsou přizpůsobení odebráním dokument s názvem **WordDocument1.docx** se na ploše.  
  
     [!code-csharp[Trin_VstcoreDeployment#2](../vsto/codesnippet/CSharp/Trin_VstcoreDeploymentCS/Program.cs#2)]
     [!code-vb[Trin_VstcoreDeployment#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreDeploymentVB/Program.vb#2)]  
  
4.  Sestavte projekt a spusťte aplikaci v počítači, ve které chcete odebrat přizpůsobení. Počítač musí mít Visual Studio 2010 Tools for Office Runtime nainstalována.  
  
## <a name="see-also"></a>Viz také  
 [Správa dokumentů na serveru s použitím třídy ServerDocument](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)   
 [Postupy: Připojení rozšíření spravovaného kódu k dokumentům](../vsto/how-to-attach-managed-code-extensions-to-documents.md)  
  
  