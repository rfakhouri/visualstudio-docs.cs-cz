---
title: "Služba Essentials | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- services, essentials
ms.assetid: fbe84ad9-efe1-48b1-aba3-b50b90424d47
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 4db5404ed4cb307064d9d913c240b16051c25977
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="service-essentials"></a>Služba Essentials
Služba je smlouva mezi dvěma VSPackages. Jeden VSPackage poskytuje konkrétní sadu rozhraní pro jiné VSPackage využívat. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]je kolekce VSPackages, která poskytuje služby do jiných VSPackages.  
  
 Například můžete použít službu SVsActivityLog získat rozhraní IVsActivityLog, který můžete použít k zápisu do protokolu činnosti. Další informace najdete v tématu [postupy: použití protokolu činnosti](../../extensibility/how-to-use-the-activity-log.md).  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]poskytuje také některé integrované služby, které nejsou registrované. VSPackages můžete nahradit předdefinované nebo jiných služeb tím, že poskytuje přepsání služby. Pouze jedna služba přepsání je povoleno pro všechny služby.  
  
 Služby mají žádné možnosti rozpoznání. Proto musíte znát identifikátor služby (SID) služby, který chcete používat, a musíte znát rozhraní, která poskytuje. Tyto informace jsou uvedeny v dokumentaci odkaz pro danou službu.  
  
-   VSPackages, které poskytují služby, se nazývají poskytovatelé služeb.  
  
-   Služby, které jsou k dispozici na jiných VSPackages se nazývají služeb global services.  
  
-   Služby, které jsou k dispozici pouze pro VSPackage, který implementuje je, nebo do objektu, který vytváří, se nazývají místní služby.  
  
-   Služby, které nahradit vestavěné služby a služby poskytované jiné balíčky, se nazývají přepsání služby.  
  
-   Služby nebo přepsání služby jsou načtena na vyžádání, to znamená, je při službu, kterou poskytuje si vyžádá další VSPackage načteno poskytovatele služeb.  
  
-   Pro podporu načítání na vyžádání, poskytovatele služeb zaregistruje jeho služeb global services s [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Další informace najdete v tématu [postupy: poskytování služby](../../extensibility/how-to-provide-a-service.md).  
  
-   Po obdržení služby použít [QueryInterface](/cpp/atl/queryinterface) (nespravovaný kód) nebo přetypování (spravovaný kód) Chcete-li získat požadované rozhraní, například:  
  
    ```vb  
    TryCast(GetService(GetType(SVsActivityLog)), IVsActivityLog)  
    ```  
  
    ```csharp  
    GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
    ```  
  
-   Spravovaný kód odkazuje službu typem, zatímco nespravovaný kód odkazuje na službu podle její identifikátor GUID.  
  
-   Když [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] zatížení a VSPackage předává poskytovatele služeb do VSPackage, aby poskytl přístup VSPackage služeb global services. To se označuje jako "umístění" VSPackage.  
  
-   VSPackages může být poskytovatelé služeb pro objekty, které vytvoří. Například formuláře může poslat žádost o služby barva jeho rámečku, který může předat požadavek na [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
-   Spravované objekty, které jsou moc hluboko vnořené, nebo není umístěný na všech může volat <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> pro přístup ke službám global services.   
  
<a name="how-to-use-getglobalservice"></a>  
  
## <a name="use-getglobalservice"></a>Použití GetGlobalService  
  
Někdy může musíte získat službu z okna nástroje nebo řízení kontejneru, který nebyl byla umístěný, jinak má byla umístěný s poskytovatelem služby, který nebude vědět o službu, kterou chcete. Například můžete chtít zapisovat do protokolu aktivit z v rámci ovládacího prvku. Další informace o těchto a dalších scénářů najdete v tématu [postupy: řešení potíží s služby](../../extensibility/how-to-troubleshoot-services.md).  
  
Většina služeb sady Visual Studio můžete získat voláním statických <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> metoda.  
  
<xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A>závisí na službě, uložené v mezipaměti je umístěný zprostředkovatele, který je inicializován poprvé žádné VSPackage odvozené z balíčku. Musí zaručit, že tato podmínka je splněna, jinak připravit null služby.  
  
Naštěstí <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> ve většině případů funguje správně.  
  
-   Pokud VSPackage poskytuje službu, zná pouze jiné VSPackage, VSPackage žádají o služby je umístěný před VSPackage za předpokladu, že služba je načtena.  
  
-   Pokud okno nástroje je vytvořený VSPackage, je umístěný VSPackage předtím, než se vytvoří okno nástroje.  
  
-   Pokud nástroj okna vytvořeného rozhraním VSPackage je hostitelem kontejneru ovládacího prvku, je umístěný VSPackage před vytvořením kontejneru ovládacího prvku.  
  
### <a name="to-get-a-service-from-within-a-tool-window-or-control-container"></a>Získat služby z nástroj okno nebo řízení kontejneru  
  
-   Tento kód vložte do konstruktoru, okno nástroje nebo kontejneru ovládacích prvků:  
  
    ```csharp  
    IVsActivityLog log = Package.GetGlobalService(typeof(SVsActivityLog)) as IVsActivityLog;
        if (log == null) return;
    ```  
    ```vb  
    Dim log As IVsActivityLog = TryCast(Package.GetGlobalService(GetType(SVsActivityLog)), IVsActivityLog)
    If log Is Nothing Then
        Return
    End If
    ```  
    
    Tento kód získá služby SVsActivityLog a obsahuje ji IVsActivityLog rozhraní, které lze použít k zápisu do protokolu činnosti. Příklad, naleznete v části [postupy: použití protokolu činnosti](../../extensibility/how-to-use-the-activity-log.md).  
  
## <a name="see-also"></a>Viz také  
 [Seznam dostupných služeb](../../extensibility/internals/list-of-available-services.md)   
 [Použití a poskytování služeb](../../extensibility/using-and-providing-services.md)   
 [Přetypování a převody typů](/dotnet/csharp/programming-guide/types/casting-and-type-conversions)   
 [Přetypování](/cpp/cpp/casting)