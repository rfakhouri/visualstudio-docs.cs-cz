---
title: "Postupy: odstraňování potíží se službami | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: services, troubleshooting
ms.assetid: 001551da-4847-4f59-a0b2-fcd327d7f5ca
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c241b80430fd02a649efab7f8a65498e606d2804
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-troubleshoot-services"></a>Postupy: odstraňování potíží se službami
Existuje několik běžné problémy, ke kterým dochází při pokusu získat službu:  
  
-   Služba není zaregistrovaná s [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
-   Služba se požaduje typ rozhraní a ne typ služby.  
  
-   Nebyl byla umístěný VSPackage žádají o službu.  
  
-   Chybný zprostředkovatel se používá.  
  
 Pokud požadovaná služba nelze získat, volání <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> , vrátí hodnotu null. Měli byste vždy otestovat pro null po žádající o službu:  
  
```csharp  
IVsActivityLog log =   
    GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
if (log == null) return;  
```  
  
### <a name="to-troubleshoot-a-service"></a>Chcete-li vyřešit služby  
  
1.  Zkontrolujte systémového registru zobrazíte, zda služba správně zaregistrována. Další informace najdete v tématu [postupy: poskytování služby](../extensibility/how-to-provide-a-service.md).  
  
     Následující fragment souboru .reg ukazuje, jak může zaregistrovat službu SVsTextManager:  
  
    ```  
    [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\<version number>\Services\{F5E7E71D-1401-11d1-883B-0000F87579D2}]  
    @="{F5E7E720-1401-11d1-883B-0000F87579D2}"  
    "Name"="SVsTextManager"  
    ```  
  
     V předchozím příkladu číslo verze je verze [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], například 12.0 nebo 14.0, klíč {F5E7E71D-1401-11d1-883B-0000F87579D2} je služba identifikátor (SID) službu, SVsTextManager a {hodnotu výchozí F5E7E720-1401-11D1-883B-0000F87579D2} je GUID textový správce VSPackage, které poskytuje služba balíčku.  
  
2.  Při volání metody GetService použijte typ služby a není typu rozhraní. Žádosti o služby z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], <xref:Microsoft.VisualStudio.Shell.Package> extrahuje z typu GUID. Služba nebude nalezeno, pokud existují následující podmínky:  
  
    1.  Typ rozhraní je předán metody GetService místo typ služby.  
  
    2.  Žádný identifikátor GUID je explicitně přiřazena rozhraní. Proto systém vytvoří výchozí identifikátor GUID pro objekt podle potřeby.  
  
3.  Ujistěte se, že má byla umístěný VSPackage žádají o službu. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]poté, co je vytvořen a před voláním lokality VSPackage <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A>.  
  
     Pokud máte kód v VSPackage konstruktor, který vyžaduje službu, můžete ho přesunete do metoda Initialize.  
  
4.  Ujistěte se, že používáte správné služby zprostředkovatele.  
  
     Ne všichni poskytovatelé služeb jsou agentem. Poskytovatel služeb, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] předává do okna nástroje se liší od ten pak předá VSPackage. Poskytovateli nástroje okno služby ví o <xref:Microsoft.VisualStudio.Shell.Interop.STrackSelection>, ale nebude vědět o <xref:Microsoft.VisualStudio.Shell.Interop.SVsRunningDocumentTable>. Můžete volat <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> získat poskytovatele služeb VSPackage z v rámci okno nástroje.  
  
     Pokud okno nástroje hostuje uživatelský ovládací prvek nebo jiných kontejneru ovládacích prvků, bude umístěný ve model součásti systému Windows a nebudete mít přístup k jakémukoli kontejneru [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] služby. Můžete volat <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> získat poskytovatele služeb VSPackage z v kontejneru ovládacího prvku.  
  
## <a name="see-also"></a>Viz také  
 [Seznam dostupných služeb](../extensibility/internals/list-of-available-services.md)   
 [Použití a poskytování služeb](../extensibility/using-and-providing-services.md)   
 [Služba Essentials](../extensibility/internals/service-essentials.md)