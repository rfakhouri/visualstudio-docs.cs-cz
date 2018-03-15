---
title: "Postupy: poskytování služby | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- services, providing
ms.assetid: 12bc1f12-47b1-44f6-b8db-862aa88d50d1
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: d2a38a2c0830b701796b8417c69a75582c5b2f89
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2018
---
# <a name="how-to-provide-a-service"></a>Postupy: poskytování služby
VSPackage poskytuje služby, které můžete použít jiné VSPackages. K poskytování služeb, musí VSPackage Zaregistrujte službu pomocí sady Visual Studio a přidání služby.  
  
 <xref:Microsoft.VisualStudio.Shell.Package> Třída implementuje obě <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> a <xref:System.ComponentModel.Design.IServiceContainer>. <xref:System.ComponentModel.Design.IServiceContainer> obsahuje metody zpětného volání, které poskytují služby na vyžádání.  
  
 Další informace o službách najdete v tématu [služby Essentials](../extensibility/internals/service-essentials.md) .  
  
> [!NOTE]
>  Když VSPackage bude odpojen, Visual Studio čeká na všechny požadavky na služby, které poskytuje VSPackage byly dodány. Nové požadavky pro tyto služby není povoleno. By neměla explicitně volání <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService.RevokeService%2A> metoda odvolat služby při uvolnění.  
  
#### <a name="implementing-a-service"></a>Implementace služby  
  
1.  Vytvoření projektu VSIX (**soubor > Nový > Projekt > Visual C# > Rozšíření > Projekt VSIX**).  
  
2.  Do projektu přidejte VSPackage. Vyberte uzel projektu v **Průzkumníku řešení** a klikněte na tlačítko **Přidat > novou položku > Visual C# položky > Rozšíření > Balíček Visual Studio**.  
  
3.  K implementaci služby, musíte vytvořit tři typy:  
  
    -   Rozhraní, které popisuje službu. Mnoho z těchto rozhraní je prázdný, to znamená, že mají žádné metody.  
  
    -   Rozhraní, které popisuje rozhraní služby. Toto rozhraní obsahuje metody k implementaci.  
  
    -   Třída, která implementuje rozhraní služby a služby.  
  
     Následující příklad ukazuje základní implementaci všech tří typů. V konstruktoru třídy služeb, musíte nastavit poskytovatele služeb.  
  
    ```csharp  
    public class MyService : SMyService, IMyService  
    {  
        private Microsoft.VisualStudio.OLE.Interop.IServiceProvider serviceProvider;  
        private string myString;  
        public MyService(Microsoft.VisualStudio.OLE.Interop.IServiceProvider sp)  
        {  
            Trace.WriteLine(  
                   "Constructing a new instance of MyService");  
            serviceProvider = sp;  
        }  
        public void Hello()  
        {  
            myString = "hello";  
        }  
        public string Goodbye()  
        {  
           return "goodbye";  
        }  
    }  
    public interface SMyService  
    {  
    }  
    public interface IMyService  
    {  
        void Hello();  
        string Goodbye();  
    }  
  
    ```  
  
### <a name="registering-a-service"></a>Registrace služby  
  
1.  Chcete-li zaregistrovat službu, přidejte <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> k VSPackage, který poskytuje službu. Tady je příklad:  
  
    ```csharp  
    [ProvideService(typeof(SMyService))]  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
    [Guid(VSPackage1.PackageGuidString)]  
    public sealed class VSPackage1 : Package  
    {. . . }  
    ```  
  
     Tento atribut zaregistruje `SMyService` pomocí sady Visual Studio.  
  
    > [!NOTE]
    >  Chcete-li zaregistrovat službu, která nahrazuje jinou službu se stejným názvem, použijte <xref:Microsoft.VisualStudio.Shell.ProvideServiceOverrideAttribute>. Poznámka: Tento pouze jeden přepsání služby je povolen.  
  
### <a name="adding-a-service"></a>Přidání služby  
  
1.  V inicializátoru VSPackage přidání služby a přidejte metody zpětného volání k vytvoření služby. Tady je změnu provést <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> metoda:  
  
    ```csharp  
    protected override void Initialize()  
    {  
        ServiceCreatorCallback callback =new ServiceCreatorCallback(CreateService);  
  
        ((IServiceContainer)this).AddService(typeof(SMyService), callback);  
    . . .  
    }  
    ```  
  
2.  Implementace metody zpětného volání, která by měl vytvořit a vrátit služby nebo hodnota null, pokud nelze vytvořit.  
  
    ```csharp  
    private object CreateService(IServiceContainer container, Type serviceType)  
    {  
        if (typeof(SMyService) == serviceType)  
            return new MyService(this);  
        return null;  
    }  
    ```  
  
    > [!NOTE]
    >  Visual Studio můžete odmítnout žádost o poskytovat služby. Dělá to tak, pokud jiné VSPackage již poskytuje službu.  
  
3.  Teď můžete získat službu a použít její metody. Následující příklad ukazuje použití služby v inicializátoru, ale můžete získat službu kdekoli chcete používat službu.  
  
    ```csharp  
    protected override void Initialize()  
    {  
        ServiceCreatorCallback callback =new ServiceCreatorCallback(CreateService);  
  
        ((IServiceContainer)this).AddService(typeof(SMyService), callback);  
  
        MyService myService = (MyService) this.GetService(typeof(SMyService));  
        myService.Hello();  
        string helloString = myService.Goodbye();  
  
        base.Initialize();  
    }  
    ```  
  
     Hodnota `helloString` by měl být "text Hello".  
  
## <a name="see-also"></a>Viz také  
 [Postupy: získání služby](../extensibility/how-to-get-a-service.md)   
 [Použití a poskytování služeb](../extensibility/using-and-providing-services.md)   
 [Základy služeb](../extensibility/internals/service-essentials.md)
