---
title: 'Postupy: Poskytování služeb | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- services, providing
ms.assetid: 12bc1f12-47b1-44f6-b8db-862aa88d50d1
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a752e05e5a7c91e0e9f3d3c21f8542014a053245
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66324968"
---
# <a name="how-to-provide-a-service"></a>Postupy: Poskytování služeb
VSPackage může poskytovat služby, které můžete použít jiné balíčky VSPackages. Poskytování služeb, musíte VSPackage registraci služby pomocí sady Visual Studio a přidejte službu.

 <xref:Microsoft.VisualStudio.Shell.Package> Třída implementuje oba <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> a <xref:System.ComponentModel.Design.IServiceContainer>. <xref:System.ComponentModel.Design.IServiceContainer> obsahuje metody zpětného volání, které poskytují služby na vyžádání.

 Další informace o službách najdete v tématu [služby essentials](../extensibility/internals/service-essentials.md) .

> [!NOTE]
> VSPackage blížící se nenačte, Visual Studio čeká na všechny žádosti o služby, které poskytuje VSPackage byl dodán. Neumožňuje nové požadavky pro tyto služby. Neměli volat explicitně <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService.RevokeService%2A> metoda odvolání přístupu služby při uvolnění.

## <a name="implement-a-service"></a>Implementace služby

1. Vytvořte projekt VSIX (**souboru** > **nový** > **projektu** > **Visual C#**  >  **Rozšiřitelnost** > **projekt VSIX**).

2. Přidejte do projektu VSPackage. Vyberte uzel projektu v **Průzkumníka řešení** a klikněte na tlačítko **přidat** > **nová položka** > **položky Visual C#**  >  **Rozšiřitelnost** > **balíčku sady Visual Studio**.

3. K implementaci služby, je potřeba vytvořit tři typy:

   - Rozhraní, který popisuje službu. Mnohé z těchto rozhraní jsou prázdné, to znamená, že mají žádné metody.

   - Rozhraní, které popisují rozhraní služby. Toto rozhraní obsahuje metody k implementaci.

   - Třída, která implementuje služba a služba rozhraní.

     Následující příklad ukazuje základní implementaci ze tří typů. Konstruktor třídy služeb, musíte nastavit poskytovatele služeb.

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

### <a name="register-a-service"></a>Registrace služby

1. Chcete-li zaregistrovat služby, přidejte <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> VSPackage, která poskytuje služby. Tady je příklad:

    ```csharp
    [ProvideService(typeof(SMyService))]
    [PackageRegistration(UseManagedResourcesOnly = true)]
    [Guid(VSPackage1.PackageGuidString)]
    public sealed class VSPackage1 : Package
    {. . . }
    ```

     Tento atribut zaregistruje `SMyService` pomocí sady Visual Studio.

    > [!NOTE]
    > Pokud chcete zaregistrovat službu, která nahrazuje jinou se stejným názvem, použijte <xref:Microsoft.VisualStudio.Shell.ProvideServiceOverrideAttribute>. Poznámka: Tento pouze jedno přepsání služby je povolen.

### <a name="add-a-service"></a>Přidat službu

1. V inicializátoru VSPackage přidat služby a přidejte metodu zpětného volání pro vytvoření služeb. Tady je změnit tak, aby <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> metody:

    ```csharp
    protected override void Initialize()
    {
        ServiceCreatorCallback callback =new ServiceCreatorCallback(CreateService);

        ((IServiceContainer)this).AddService(typeof(SMyService), callback);
    . . .
    }
    ```

2. Implementace metody zpětného volání, které by měl vytvořit a vrátit služby nebo hodnota null, pokud nelze vytvořit.

    ```csharp
    private object CreateService(IServiceContainer container, Type serviceType)
    {
        if (typeof(SMyService) == serviceType)
            return new MyService(this);
        return null;
    }
    ```

    > [!NOTE]
    > Visual Studio může odmítnout žádost o poskytování služeb. Dělá to, pokud jiné VSPackage již poskytuje službu.

3. Nyní můžete získat službu a použijte její metody. Následující příklad ukazuje využití služby v inicializátoru, ale můžete získat službu kamkoli chcete používat službu.

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

     Hodnota `helloString` by měl být "Hello".

## <a name="see-also"></a>Viz také:
- [Postupy: Získání služby](../extensibility/how-to-get-a-service.md)
- [Použít a poskytování služeb](../extensibility/using-and-providing-services.md)
- [Základy služby](../extensibility/internals/service-essentials.md)
