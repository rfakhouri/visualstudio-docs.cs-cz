---
title: "Návod: Stahování satelitních sestavení na vyžádání pomocí rozhraní API nasazení ClickOnce | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, globalization
- localization, Windows Forms
- Windows Forms, localization
- globalization, ClickOnce
- satellite assemblies, ClickOnce
- ClickOnce deployment, on-demand download
- localization, ClickOnce deployment
- ClickOnce deployment, localization
ms.assetid: fdaa553f-a27e-44eb-a4e2-08c122105a87
caps.latest.revision: "11"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: c3c3b817975304a41181b5e346a32b0b95c4258e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api"></a>Návod: Stahování satelitních sestavení na vyžádání pomocí rozhraní API nasazení ClickOnce
Aplikace Windows Forms lze nakonfigurovat pro více jazykových verzí prostřednictvím satelitní sestavení. A *satelitní sestavení* je sestavení obsahující prostředky aplikace pro jazykovou verzi než výchozí jazykovou verzi aplikace.  
  
 Jak je popsáno v [lokalizace aplikací ClickOnce](../deployment/localizing-clickonce-applications.md), může obsahovat více satelitní sestavení pro více jazykových verzí v téže [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení. Ve výchozím nastavení [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] stáhne všechny satelitní sestavení ve vašem nasazení na klientský počítač, i když jednoho klienta, bude pravděpodobně vyžadovat pouze jedno satelitní sestavení.  
  
 Tento návod ukazuje, jak označit vaše satelitní sestavení jako volitelné a stáhnout pouze sestavení, klientský počítač potřebuje pro jeho aktuální nastavení jazykové verze. Následující postup používá nástrojů dostupných v [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]. Můžete také provést tuto úlohu v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  Viz také [návod: stahování satelitních sestavení na vyžádání pomocí ClickOnce pomocí rozhraní API nasazení návrháře](http://msdn.microsoft.com/library/ms366788\(v=vs.110\)) nebo [návod: stahování satelitních sestavení na vyžádání pomocí rozhraní API nasazení ClickOnce Pomocí návrháře](http://msdn.microsoft.com/library/ms366788\(v=vs.120\)).  
  
> [!NOTE]
>  Pro účely testování následující příklad kódu prostřednictvím kódu programu Nastaví jazykovou verzi na `ja-JP`. Najdete v části "Další kroky" dál v tomto tématu informace o tom, jak upravit tento kód pro produkční prostředí.  
  
## <a name="prerequisites"></a>Požadavky  
 Toto téma předpokládá, že víte, jak přidat lokalizované prostředky do vaší aplikace pomocí sady Visual Studio. Podrobné pokyny najdete v tématu [návod: lokalizace Windows Forms](https://msdn.microsoft.com/en-us/library/vstudio/y99d1cd3\(v=vs.100\).aspx).  
  
### <a name="to-download-satellite-assemblies-on-demand"></a>Chcete-li stáhnout satelitních sestavení na vyžádání  
  
1.  Přidejte následující kód do vaší aplikace pro povolení stahování satelitních sestavení na vyžádání.  
  
     [!code-csharp[ClickOnce.SatelliteAssembliesSDK#1](../deployment/codesnippet/CSharp/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api_1.cs)]
     [!code-vb[ClickOnce.SatelliteAssembliesSDK#1](../deployment/codesnippet/VisualBasic/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api_1.vb)]  
  
2.  Generování satelitní sestavení pro aplikaci pomocí [Resgen.exe (Generátor zdrojových souborů)](/dotnet/framework/tools/resgen-exe-resource-file-generator) nebo [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
3.  Generovat manifest aplikace, nebo otevřete stávající manifest aplikace pomocí MageUI.exe. Další informace o tomto nástroji najdete v tématu [MageUI.exe (generování manifestu a nástroj pro úpravy, grafický klient)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client).  
  
4.  Klikněte **soubory** kartě.  
  
5.  Klikněte **třemi tečkami** tlačítko (**...** ) a vyberte adresář obsahující všechny sestavení a soubory, včetně satelitní sestavení, který jste vygenerovali pomocí Resgen.exe vaší aplikace. (Satelitní sestavení bude mít název ve tvaru *isoCode*\ApplicationName.resources.dll, kde *isoCode* je identifikátor jazyka ve formátu RFC 1766.)  
  
6.  Klikněte na tlačítko **vyplnit** na přidání souborů do vašeho nasazení.  
  
7.  Vyberte **volitelné** políčko u každé satelitní sestavení.  
  
8.  Nastavte pole skupiny pro každé satelitní sestavení pro jeho identifikátoru jazyk ISO. Například by pro japonské satelitní sestavení, zadejte název skupiny stažení `ja-JP`. Tato akce povolí kód, který jste přidali v kroku 1, chcete-li stáhnout odpovídající satelitní sestavení, v závislosti na uživatele <xref:System.Threading.Thread.CurrentUICulture%2A> nastavení vlastnosti.  
  
## <a name="next-steps"></a>Další kroky  
 V produkčním prostředí, budete pravděpodobně muset odebrat řádek v příkladu kódu, který nastaví <xref:System.Threading.Thread.CurrentUICulture%2A> na určitou hodnotu, protože klientské počítače budou mít správnou hodnotu ve výchozím nastavení. Pokud vaše aplikace běží v japonské klientský počítač, například <xref:System.Threading.Thread.CurrentUICulture%2A> bude `ja-JP` ve výchozím nastavení. Nastavení této hodnoty prostřednictvím kódu programu je vhodné pro testování vašich satelitních sestavení před nasazením aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Lokalizace aplikací ClickOnce](../deployment/localizing-clickonce-applications.md)