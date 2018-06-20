---
title: 'Návod: Stahování satelitních sestavení na vyžádání pomocí nasazení ClickOnce pomocí návrháře rozhraní API | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Windows Forms, globalization
- ClickOnce deployment, globalization
- localization, Windows Forms
- ClickOnce, on-demand download
- Windows Forms, localization
- ClickOnce deployment, localization
- walkthroughs, localization
ms.assetid: 82b85a47-b223-4221-a17c-38a52c3fb6e2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6438bbb905244902a8f5407a2ad8dea74430c430
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/19/2018
ms.locfileid: "36233461"
---
# <a name="walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer"></a>Návod: Stahování satelitních sestavení na vyžádání pomocí rozhraní API nasazení ClickOnce pomocí Návrháře
Aplikace Windows Forms lze nakonfigurovat pro více jazykových verzí prostřednictvím satelitní sestavení. A *satelitní sestavení* je sestavení obsahující prostředky aplikace pro jazykovou verzi než výchozí jazykovou verzi aplikace.  
  
 Jak je popsáno v [lokalizace aplikací ClickOnce](../deployment/localizing-clickonce-applications.md), může obsahovat více satelitní sestavení pro více jazykových verzí v téže [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení. Ve výchozím nastavení [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] stáhne všechny satelitní sestavení ve vašem nasazení na klientský počítač, i když jednoho klienta, bude pravděpodobně vyžadovat pouze jedno satelitní sestavení.  
  
 Tento návod ukazuje, jak označit vaše satelitní sestavení jako volitelné a stáhnout pouze sestavení, klientský počítač potřebuje pro jeho aktuální nastavení jazykové verze.  
  
> [!NOTE]
>  Pro účely testování následující příklady kódu programově nastavit jazykovou verzi `ja-JP`. Najdete v části "Další kroky" dál v tomto tématu informace o tom, jak upravit tento kód pro produkční prostředí.  
  
### <a name="to-mark-satellite-assemblies-as-optional"></a>Označit jako volitelné satelitní sestavení  
  
1.  Sestavte projekt. Tím se vygeneruje satelitní sestavení pro všechny jazykové verze, které jsou lokalizace do.  
  
2.  Klikněte pravým tlačítkem na název projektu v Průzkumníku řešení a klikněte na tlačítko **vlastnosti**.  
  
3.  Klikněte **publikovat** a pak klikněte **soubory aplikace**.  
  
4.  Vyberte **zobrazit všechny soubory** zaškrtnutím políčka Zobrazit satelitní sestavení. Ve výchozím nastavení všechny satelitní sestavení budou zahrnuty ve vašem nasazení a budou viditelné v tomto dialogovém.  
  
     Satelitní sestavení bude mít název ve tvaru *isoCode*\ApplicationName.resources.dll, kde *isoCode* je identifikátor jazyka ve formátu RFC 1766.  
  
5.  Klikněte na tlačítko **nový** v **Skupina stažení** seznamu pro každý jazyk identifikátor. Po zobrazení výzvy k názvu skupiny stahování, zadejte identifikátor jazyka. Například by pro japonské satelitní sestavení, zadejte název skupiny stažení `ja-JP`.  
  
6.  Zavřít **soubory aplikace** dialogové okno.  
  
### <a name="to-download-satellite-assemblies-on-demand-in-c"></a>Chcete-li stáhnout satelitních sestavení na vyžádání v jazyce C# #
  
1.  Otevřete soubor Program.cs. Pokud nevidíte tento soubor v Průzkumníku řešení, vyberte projekt a na **projektu** nabídky, klikněte na tlačítko **zobrazit všechny soubory**.  
  
2.  Použijte následující kód ke stažení odpovídající satelitní sestavení a spuštění aplikace.  
  
     [!code-csharp[ClickOnce.SatelliteAssemblies#1](../deployment/codesnippet/CSharp/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_1.cs)]  
  
### <a name="to-download-satellite-assemblies-on-demand-in-visual-basic"></a>Chcete-li stáhnout satelitních sestavení na vyžádání v jazyce Visual Basic  
  
1.  V **vlastnosti** okna pro aplikace, klikněte **aplikace** kartě.  
  
2.  V dolní části stránky karty, klikněte na tlačítko **zobrazení události aplikace**.  
  
3.  Přidejte následující importy na začátek souboru ApplicationEvents.VB.  
  
     [!code-vb[ClickOnce.SatelliteAssembliesVB#1](../deployment/codesnippet/VisualBasic/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_2.vb)]  
  
4.  Přidejte následující kód, který `MyApplication` třídy.  
  
     [!code-vb[ClickOnce.SatelliteAssembliesVB#2](../deployment/codesnippet/VisualBasic/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_3.vb)]  
  
## <a name="next-steps"></a>Další kroky  
 V produkčním prostředí, budete pravděpodobně muset odebrat řádek z příkladů kódu, který nastaví <xref:System.Threading.Thread.CurrentUICulture%2A> na určitou hodnotu, protože klientské počítače budou mít správnou hodnotu ve výchozím nastavení. Pokud vaše aplikace běží v japonské klientský počítač, například <xref:System.Threading.Thread.CurrentUICulture%2A> bude `ja-JP` ve výchozím nastavení. Nastavení programu je vhodné pro testování vašich satelitních sestavení před nasazením aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Návod: Stahování satelitních sestavení na vyžádání pomocí rozhraní API nasazení ClickOnce](../deployment/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api.md)   
 [Lokalizace aplikací ClickOnce](../deployment/localizing-clickonce-applications.md)
