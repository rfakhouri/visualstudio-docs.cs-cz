---
title: "Postupy: vytvoření vlastní Text značek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - custom text markers
ms.assetid: 6e32ed81-c604-4a32-9012-8db3bec7c846
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0ab395fdb8c06e643c76ee0918b8a626abb756cb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-custom-text-markers"></a>Postupy: vytvoření vlastní Text značek
Pokud chcete vytvořit vlastní text značku zdůraznil nebo uspořádání kódu, musíte provést následující kroky:  
  
-   Registrovat nový text značky, tak, aby dalších nástrojů k němu přístup  
  
-   Zadejte výchozí implementace a konfigurace text značky  
  
-   Vytvoření služby, který můžete použít další procesy, aby používat značky textu  
  
 Podrobnosti o tom, jak použít značku text v oblasti kódu najdete v tématu [postupy: použití Text značek](../extensibility/how-to-use-text-markers.md).  
  
### <a name="to-register-a-custom-marker"></a>Chcete-li zaregistrovat vlastní značky  
  
1.  Vytvořte položku registru takto:  
  
     HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\\*\<verze >*\Text Editor\External značek\\*\<MarkerGUID >*  
  
     *\<MarkerGUID >*je `GUID` použít k identifikaci značky, který chcete přidat  
  
     *\<Verze >* je verze [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], například 8.0  
  
     *\<PackageGUID >* je identifikátor GUID VSPackage implementace objekt automatizace.  
  
    > [!NOTE]
    >  Kořenové cestě HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\\*\<verze >* monitorconfigurationoverride lze přepsat alternativní kořenové při inicializaci prostředí sady Visual Studio, další informace najdete v tématu, [Přepínače příkazového řádku](../extensibility/command-line-switches-visual-studio-sdk.md).  
  
2.  Vytvořit čtyři hodnoty v části HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\\*\<verze >*\Text Editor\External značek\\*\<MarkerGUID >*  
  
    -   (Výchozí)  
  
    -   Služba  
  
    -   displayName  
  
    -   Balíček  
  
    -   `Default`je typ REG_SZ volitelné položky. Pokud nastavíte, hodnotu položky je řetězec obsahující některé užitečné identifikační informace, například "vlastní Text značky".  
  
    -   `Service`je typ REG_SZ položky obsahující řetězec identifikátor GUID služby, která poskytuje vlastní text značky tím, že proffering <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerTypeProvider>. Není ve formátu {XXXXXX XXXX XXXX XXXX XXXXXXXXX}.  
  
    -   `DisplayName`je typ REG_SZ položky obsahující ID prostředku názvu značky vlastní text. Formát je #YYYY.  
  
    -   `Package`je záznam obsahující typ REG_SZ `GUID` VSPackage, která poskytuje služby uvedené v části služby. Není ve formátu {XXXXXX XXXX XXXX XXXX XXXXXXXXX}.  
  
### <a name="to-create-a-custom-text-marker"></a>Chcete-li vytvořit vlastní text značky  
  
1.  Implementace <xref:Microsoft.VisualStudio.TextManager.Interop.IVsPackageDefinedTextMarkerType> rozhraní.  
  
     Implementace tohoto rozhraní definuje chování a vzhled vašeho typu vlastní značky.  
  
     Toto rozhraní je volána, když  
  
    1.  Uživatel spustí první rozhraní IDE.  
  
    2.  Uživatel vybere **obnovit výchozí nastavení** tlačítko pod **písma a barev** stránka vlastností v **prostředí** složky umístěné na levém podokně  **Možnosti** dialogové okno získaný **nástroje** nabídky rozhraní IDE.  
  
2.  Implementace <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerTypeProvider.GetTextMarkerType%2A> metody, které zadání `IVsPackageDefinedTextMarkerType` implementace by měl být vrácených na základě typ značky zadaný ve volání metody identifikátor GUID.  
  
     Prostředí zavolá tato metoda první čas typ vaše vlastní značky se vytvoří a určuje identifikátor GUID identifikace typ vlastní značky.  
  
### <a name="to-proffer-your-marker-type-as-a-service"></a>Chcete-li proffer vašeho typu značky jako služby  
  
1.  Volání <xref:Microsoft.VisualStudio.OLE.Interop.IOleComponentManager.QueryService%2A> metodu pro <xref:Microsoft.VisualStudio.Shell.Interop.SProfferService>.  
  
     Ukazatel na <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService> je vrácen.  
  
2.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService.ProfferService%2A> metoda, zadání identifikátoru GUID identifikace služby typu vlastní značky a poskytování ukazatel na vaši implementaci <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> rozhraní. Vaše <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> implementace by měla vrátit ukazatel na vaši implementaci <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerTypeProvider> rozhraní.  
  
     Jedinečný soubor cookie identifikace, že je vaše služba vrátila. Později můžete tento soubor cookie k odvolání služby typu vlastní značky voláním <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService.RevokeService%2A> metodu <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService> rozhraní pro tuto hodnotu souboru cookie.  
  
## <a name="see-also"></a>Viz také  
 [Text značky pomocí starší verze rozhraní API](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [Postupy: Přidání značek standardního textu](../extensibility/how-to-add-standard-text-markers.md)   
 [Postupy: implementace chyba značky](../extensibility/how-to-implement-error-markers.md)   
 [Postupy: použití značek textu](../extensibility/how-to-use-text-markers.md)