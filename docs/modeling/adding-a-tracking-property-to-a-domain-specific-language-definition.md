---
title: "Přidání vlastnosti sledování k definici jazyka domény | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tracking properties [Domain-Specific Language Tools], walkthrough
- Domain-Specific Language Tools, walkthroughs
- walkthroughs [Domain-Specific Language Tools]
ms.assetid: 4aa47777-de75-4897-a423-a3c4426b4125
caps.latest.revision: "22"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: a126524672b0b827d278d2d76c01d907c9d403a1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="adding-a-tracking-property-to-a-domain-specific-language-definition"></a>Přidání vlastnosti sledování do definice jazyka specifického pro doménu
Tento návod ukazuje, jak přidat vlastnost sledování do modelu domény.  
  
 A *sledování domény* je vlastnost, která lze aktualizovat pomocí uživatele, ale které má výchozí hodnotu, která se počítá pomocí hodnot jiných vlastnosti domény nebo elementy.  
  
 Například v jazykové nástroje specifické pro doménu (DSL Tools) zobrazovaný název vlastnosti třídy domény má výchozí hodnotu, která se počítá pomocí názvu třídy domény, ale uživatel změňte hodnotu v době návrhu nebo ho resetovat do počítaná hodnota.  
  
 V tomto návodu vytvoříte jazyk specifické pro doménu (DSL), který má Namespace, sledování vlastnost, která má výchozí hodnotu na základě Namespace výchozí vlastnosti modelu. Další informace o sledování vlastnosti najdete v tématu [definování vlastnosti sledování](http://msdn.microsoft.com/en-us/0538b0e4-6221-4e7d-911a-b92cd622f0be).  
  
-   Podpora nástroje DSL, sledování popisovače vlastnosti. Návrháře DSL však nelze použít k přidání vlastnosti sledování jazyka. Proto je nutné přidat vlastní kód definovat a implementovat vlastnost sledování.  
  
 Vlastnost sledování má dva stavy: sledováním a aktualizované uživatelem. Vlastnosti sledování mají následující funkce:  
  
-   Ve sledování stavu, hodnota vlastnosti sledování je vypočtena a hodnota se aktualizuje jako ostatní vlastnosti v modelu změn.  
  
-   Když v aktualizaci ve stavu uživatele, hodnota vlastnosti sledování uchovává hodnotu, do které uživatel poslední nastavit vlastnost.  
  
-   V **vlastnosti** okně **resetovat** příkaz pro vlastnost sledování je povoleno pouze pokud je vlastnost v aktualizaci podle stavu uživatele. **Resetovat** příkaz nastaví vlastnost sledování stavu pro sledování.  
  
-   V **vlastnosti** okno, pokud je vlastnost sledování v sledování stavu, jeho hodnota se zobrazí v pravidelných písmo.  
  
-   V **vlastnosti** okno, pokud je vlastnost sledování v aktualizaci ve stavu uživatele, je jeho hodnota zobrazí tučným písmem.  
  
## <a name="prerequisites"></a>Požadavky  
 Před zahájením tohoto návodu, musíte nejprve nainstalovat tyto komponenty:  
  
|||  
|-|-|  
|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]|[http://go.microsoft.com/fwlink/?LinkId=185579](http://go.microsoft.com/fwlink/?LinkID=185579)|  
|[!INCLUDE[vssdk_current_short](../modeling/includes/vssdk_current_short_md.md)]|[http://go.microsoft.com/fwlink/?LinkId=185580](http://go.microsoft.com/fwlink/?LinkID=185580)|  
|[!INCLUDE[dsl](../modeling/includes/dsl_md.md)]|[http://go.microsoft.com/fwlink/?LinkId=185581](http://go.microsoft.com/fwlink/?LinkID=185581)|  
  
## <a name="creating-the-dsl-project"></a>Vytvořením DSL projektu  
 Vytvoření projektu pro váš jazyk specifické pro doménu.  
  
#### <a name="to-create-the-project"></a>Vytvoření projektu  
  
1.  Vytvoření projektu jazyka Návrhář specifické pro doménu. Pojmenujte ji `TrackingPropertyDSL`.  
  
2.  V **specifické pro doménu jazyk Návrhář průvodce**, nastavte následující možnosti:  
  
    1.  Vyberte **MinimalLanguage** šablony.  
  
    2.  Použít výchozí název pro daný jazyk specifické pro doménu, `TrackingPropertyDSL`.  
  
    3.  Nastavit rozšíření pro model souborů `trackingPropertyDsl`.  
  
    4.  Ikona výchozí šablony použijte pro soubory modelu.  
  
    5.  Nastavte název produktu `Product Name`.  
  
    6.  Nastavte na název společnosti na `Company Name`.  
  
    7.  Použijte výchozí hodnotu pro kořenový obor názvů pro projekty v řešení, `CompanyName.ProductName.TrackingPropertyDSL`.  
  
    8.  Povolí průvodce vytvořte soubor klíče se silným názvem pro vaše sestavení.  
  
    9. Zkontrolujte podrobnosti o řešení a pak klikněte na tlačítko **Dokončit** a vytvořte tak projekt DSL definice.  
  
## <a name="customizing-the-default-dsl-definition"></a>Přizpůsobení výchozí definici DSL  
 V této části můžete přizpůsobit definici DSL tak, aby obsahovala následující položky:  
  
-   Namespace, sledování vlastnost pro každý element modelu.  
  
-   Logická hodnota IsNamespaceTracking vlastnost pro každý element modelu. Tato vlastnost označí, zda vlastnost sledování je v stavu sledování nebo v aktualizaci podle stavu uživatele.  
  
-   Namespace výchozí vlastnost pro model. Tato vlastnost se použije k výpočtu výchozí hodnotu Namespace vlastnost sledování.  
  
-   Vlastnost CustomElements vypočítat pro model. Tato vlastnost bude znamenat podíl prvky, které mají vlastní obor názvů.  
  
#### <a name="to-add-the-domain-properties"></a>Chcete-li přidat vlastnosti domény  
  
1.  V Návrháři DSL, klikněte pravým tlačítkem myši **ExampleModel** třídy domény, přejděte na příkaz **přidat**a potom klikněte na **vlastnost DomainProperty**.  
  
    1.  Název nové vlastnosti `DefaultNamespace`.  
  
    2.  V **vlastnosti** okna pro novou vlastnost, nastavte **výchozí hodnotu** k `DefaultNamespace`a nastavte **typ** k **řetězec**.  
  
2.  Na **ExampleModel** domény třídy, přidejte domény vlastnost s názvem `CustomElements`.  
  
     V **vlastnosti** okna pro novou vlastnost, nastavte **druhu** k **vypočítaná**.  
  
3.  Na **ExampleElement** domény třídy, přidejte domény vlastnost s názvem `Namespace`.  
  
     V **vlastnosti** okna pro novou vlastnost, nastavte **je Procházet** k **False**a nastavte **druhu** k **CustomStorage** .  
  
4.  Na **ExampleElement** domény třídy, přidejte domény vlastnost s názvem `IsNamespaceTracking`.  
  
     V **vlastnosti** okna pro novou vlastnost, nastavte **je Procházet** k **False**, nastavte **výchozí hodnotu** k `true`a nastavte **Typ** k **Boolean**.  
  
#### <a name="to-update-the-diagram-elements-and-dsl-details"></a>Chcete-li aktualizovat elementy diagramu a podrobnosti DSL  
  
1.  V Návrháři DSL, klikněte pravým tlačítkem myši **ExampleShape** geometrické obrazce, přejděte na příkaz **přidat**a potom klikněte na **Text Dekoratéra**.  
  
    1.  Název nové dekoratéra text `NamespaceDecorator`.  
  
    2.  V **vlastnosti** okna pro text dekoratéra, nastavte **pozice** k **InnerBottomLeft**.  
  
2.  V Návrháři DSL, vyberte řádek, který připojí **ExampleElement** třídy k **ExampleShape** tvaru.  
  
    1.  V **DSL podrobnosti** vyberte **Dekoratéra mapy** kartě.  
  
    2.  V **Dekoratéry** seznamu, vyberte **NamespaceDecorator**, zaškrtněte příslušné políčko a pak na **zobrazit vlastnosti** seznamu, vyberte **Namespace**.  
  
3.  V **DSL Průzkumníka**, rozbalte položku **třídy domény** složky, klikněte pravým tlačítkem myši **ExampleElement** uzel a pak klikněte na tlačítko **přidat nové domény popisovač typu**.  
  
    1.  Rozbalte **ExampleElement** uzel a vyberte možnost **popisovač typu vlastní (popisovač typu domény)** uzlu.  
  
    2.  V **vlastnosti** okna pro popisovač typu domény, nastavte **vlastní programového** k **True**.  
  
4.  V **DSL Explorer**, vyberte **chování serializace Xml** uzlu.  
  
    1.  V **vlastnosti** nastavte **vlastní Post zatížení** k **True**.  
  
## <a name="transforming-templates"></a>Transformace šablony  
 Teď, když jste definovali domény třídy a vlastnosti pro vaše DSL, můžete ověřit, že definici DSL lze je transformovat správně znovu vygenerovat kód pro váš projekt.  
  
#### <a name="to-transform-the-text-templates"></a>K transformaci textové šablony  
  
1.  Na **Průzkumníku řešení** nástrojů klikněte na tlačítko **transformaci všech šablon**.  
  
2.  Systém znovu generuje kód pro řešení a uloží DslDefinition.dsl. Informace o formátu XML souborů definic najdete v tématu [DslDefinition.dsl soubor](../modeling/the-dsldefinition-dsl-file.md).  
  
## <a name="creating-files-for-custom-code"></a>Vytváření souborů pro vlastní kód  
 Pokud jste proveďte transformaci všech šablon, generuje systém zdrojový kód, který definuje jazyka specifické pro doménu v projektech Dsl a DslPackage. Tak, aby zasahovala do činnosti vygenerovaný text se můžete vyhnout, napište vlastní kód v souborech, které se liší od soubory generovaného kódu.  
  
 Je nutné zadat kód pro údržbu hodnota a stavu vaší vlastnosti sledování. Vám pomůže rozlišit vlastní kód z generovaného kódu a vyhnout se konfliktům pojmenování souboru, váš vlastní kód soubory umístěte do samostatné podsložky.  
  
#### <a name="to-create-the-code-files"></a>Postup vytvoření souborů kódu  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **DSL** projektu, přejděte na **přidat**a potom klikněte na **novou složku**. Název nové složky `CustomCode`.  
  
2.  Klikněte pravým tlačítkem na nový **CustomCode** složku, přejděte na příkaz **přidat**a potom klikněte na **novou položku**.  
  
3.  Vyberte **souboru kódu** šablony, nastavte **název** k `NamespaceTrackingProperty.cs`a potom klikněte na **OK**.  
  
     NamespaceTrackingProperty.cs soubor je vytvořen a po otevření k úpravám.  
  
4.  Ve složce vytvořte tyto soubory kódu: `ExampleModel.cs,``HelperClasses.cs`, `Serialization.cs`, a `TypeDescriptor.cs`.  
  
5.  V **DslPackage** projektu, taky vytvořit `CustomCode` složku a přidejte do ní `Package.cs` souboru kódu.  
  
## <a name="adding-helper-classes-to-support-tracking-properties"></a>Přidání pomocné třídy pro podporu sledování vlastnosti  
 Chcete-li soubor HelperClasses.cs, přidejte `TrackingHelper` a `CriticalException` třídy následujícím způsobem. Tyto třídy dále v tomto návodu budete odkazovat.  
  
#### <a name="to-add-the-helper-classes"></a>Chcete-li přidat pomocné třídy  
  
1.  Přidejte následující kód do souboru HelperClasses.cs.  
  
    ```csharp  
    using System;  
    using System.Collections;  
    using System.Diagnostics;  
    using Microsoft.VisualStudio.Modeling;  
  
    namespace CompanyName.ProductName.TrackingPropertyDSL  
    {  
        internal static class TrackingHelper  
        {  
            /// <summary>Notify each model element in a collection that a tracked  
            /// property has changed.</summary>  
            /// <param name="store">The store for the model.</param>  
            /// <param name="collection">The collection of model elements that  
            /// contain the tracking property.</param>  
            /// <param name="propertyId">The ID of the tracking property.</param>  
            /// <param name="trackingPropertyId">The ID of the property that  
            /// indicates whether the tracking property is tracking.</param>  
            internal static void UpdateTrackingCollectionProperty(  
                Store store,  
                IEnumerable collection,  
                Guid propertyId,  
                Guid trackingPropertyId)  
            {  
                DomainPropertyInfo propInfo =  
                    store.DomainDataDirectory.GetDomainProperty(propertyId);  
  
                DomainPropertyInfo trackingPropInfo =  
                    store.DomainDataDirectory.GetDomainProperty(trackingPropertyId);  
  
                Debug.Assert(propInfo != null);  
                Debug.Assert(trackingPropInfo != null);  
                Debug.Assert(trackingPropInfo.PropertyType.Equals(typeof(bool)),  
                    "Tracking property not specified as a boolean");  
  
                foreach (ModelElement element in collection)  
                {  
                    // If the tracking property is currently tracking, then notify  
                    // it that the tracked property has changed.  
                    bool isTracking = (bool)trackingPropInfo.GetValue(element);  
                    if (isTracking)  
                    {  
                        propInfo.NotifyValueChange(element);  
                    }  
                }  
            }  
        }  
  
        /// <summary>Helper class to flag critical exceptions from ones that are  
        /// safe to ignore.</summary>  
        internal static class CriticalException  
        {  
            /// <summary>Gets whether an exception is critical and can not be  
            /// ignored.</summary>  
            /// <param name="ex">The exception to check.</param>  
            /// <returns>True if the exception is critical.</returns>  
            internal static bool IsCriticalException(Exception ex)  
            {  
                if (ex is NullReferenceException  
                    || ex is StackOverflowException  
                    || ex is OutOfMemoryException  
                    || ex is System.Threading.ThreadAbortException)  
                    return true;  
  
                if (ex.InnerException != null)  
                    return IsCriticalException(ex.InnerException);  
  
                return false;  
            }  
        }  
    }  
    ```  
  
## <a name="adding-custom-code-for-the-custom-type-descriptor"></a>Přidání vlastního kódu pro popisovače vlastního typu  
 Implementace `GetCustomProperties` metodu pro popisovač typu pro `ExampleModel` třída domény.  
  
> [!NOTE]
>  Kód, který nástroje DSL vytvořit pro vlastní typ popisovač pro `ExampleModel` volání `GetCustomProperties`, nicméně nástroje DSL nevydávají kód, který implementuje metodu.  
  
 Definování tato metoda vytvoří sledování vlastnost popisovač Namespace vlastnost sledování. Navíc poskytuje atributy pro vlastnost sledování umožňuje **vlastnosti** okno ke správnému zobrazení vlastnost.  
  
#### <a name="to-modify-the-type-descriptor-for-the-examplemodel-domain-class"></a>Změnit popisovač typu pro třídu ExampleModel domény  
  
1.  Přidejte následující kód do souboru TypeDescriptor.cs.  
  
    ```csharp  
    using System;  
    using System.ComponentModel;  
    using Microsoft.VisualStudio.Modeling;  
    using Microsoft.VisualStudio.Modeling.Design;  
  
    namespace CompanyName.ProductName.TrackingPropertyDSL  
    {  
        // To the custom type descriptor for the ExampleElement domain class, add  
        // the GetCustomProperties method.  
        public partial class ExampleElementTypeDescriptor  
        {  
            /// <summary>Returns the property descriptors for the described  
            /// ExampleElement domain class.</summary>  
            /// <remarks>This method adds the tracking property descriptor.  
            /// </remarks>  
            private PropertyDescriptorCollection GetCustomProperties(  
                Attribute[] attributes)  
            {  
                // Get the default property descriptors from the base class  
                PropertyDescriptorCollection propertyDescriptors =  
                    base.GetProperties(attributes);  
  
                // Get a reference to the model element that is being described.  
                ExampleElement source = this.ModelElement as ExampleElement;  
  
                //Add the descriptor for the tracking property.  
                if (source != null)  
                {  
                    DomainPropertyInfo domainProperty =  
                        source.Store.DomainDataDirectory.GetDomainProperty(  
                            ExampleElement.NamespaceDomainPropertyId);  
  
                    DomainPropertyInfo trackingProperty =  
                        source.Store.DomainDataDirectory.GetDomainProperty(  
                            ExampleElement.IsNamespaceTrackingDomainPropertyId);  
  
                    // Define attributes for the tracking property so that the  
                    // Properties window displays the property correctly.  
                    Attribute[] attr = new Attribute[] {  
                        new DisplayNameAttribute("Element Namespace"),  
                        new DescriptionAttribute("The namespace of the element."),  
                        new CategoryAttribute("Tracking Properties"),  
                    };  
  
                    propertyDescriptors.Add(new TrackingPropertyDescriptor(  
                        source, domainProperty, trackingProperty, attr));  
                }  
  
                // Return the property descriptors for this element  
                return propertyDescriptors;  
            }  
        }  
    }  
    ```  
  
## <a name="adding-custom-code-for-the-package"></a>Přidání vlastního kódu pro balíček  
 Generovaný kód definuje typ zprostředkovatele popis pro třídu domény ExampleElement; Nicméně je nutné přidat kód dáte pokyn, aby DSL použití tohoto typu popis zprostředkovatele.  
  
#### <a name="to-update-the-dsl-package-to-use-your-custom-type-descriptor"></a>Chcete-li aktualizovat DSL balíček k použití vašeho vlastního popisovače typu  
  
1.  Přidejte následující kód do souboru Package.cs.  
  
    ```csharp  
    using System.ComponentModel;  
  
    namespace CompanyName.ProductName.TrackingPropertyDSL  
    {  
        // Override the default Initialize method.  
        internal sealed partial class TrackingPropertyDSLPackage  
        {  
            protected override void Initialize()  
            {  
                // Add the custom type descriptor for the ExampleElement type.  
                TypeDescriptor.AddProvider(  
                    new ExampleElementTypeDescriptionProvider(),  
                    typeof(ExampleElement));  
  
                base.Initialize();  
            }  
        }  
    }  
    ```  
  
## <a name="adding-custom-code-for-the-model"></a>Přidání vlastního kódu pro Model  
 Implementace `GetCustomElementsValue` metodu `ExampleModel` třída domény.  
  
> [!NOTE]
>  Kód, který nástroje DSL generovat pro `ExampleModel` volání `GetCustomElementsValue`, nicméně nástroje DSL nevydávají kód, který implementuje metodu.  
  
 Definování `GetCustomElementsValue` metoda obsahuje logiku pro vlastnost CustomElements vypočítat `ExampleModel`. Tato metoda vrátí počet `ExampleElement` domény tříd, které mají Namespace, sledování vlastnost, která má hodnotu uživatel aktualizoval a vrátí řetězec, který představuje tento počet jako podíl celkový počet elementů v modelu.  
  
 Také přidat `OnDefaultNamespaceChanged` metodu `ExampleModel`a přepsat `OnValueChanged` metodu `DefaultNamespacePropertyHandler` vnořené třídy `ExampleModel` volat `OnDefaultNamespaceChanged`.  
  
 Protože DefaultNamespace vlastnost se používá k výpočtu Namespace sledování vlastnost `ExampleModel` musíte upozornit všechny `ExampleElement` třídy domény, které hodnota DefaultNamespace změněna.  
  
#### <a name="to-modify-the-property-handler-for-the-tracked-property"></a>Chcete-li upravit obslužnou rutinu vlastnost pro vlastnost sledovaných  
  
1.  Přidejte následující kód do souboru ExampleModel.cs.  
  
    ```csharp  
    using System.Linq;  
  
    namespace CompanyName.ProductName.TrackingPropertyDSL  
    {  
        public partial class ExampleModel  
        {  
            public string GetCustomElementsValue()  
            {  
                if (this.Elements.Count == 0) return "0/0";  
  
                int number = this.Elements.Count(e => !e.IsNamespaceTracking);  
                return string.Format("{0}/{1}", number, this.Elements.Count);  
            }  
  
            #region Value changed handler for the tracked property  
  
            // When a tracked property changes, it needs to notify all of the properties  
            // that track it.  
  
            /// <summary>Called by the DefaultNamespace property value handler when the  
            /// DefaultNamespace property changes.</summary>  
            /// <param name="oldValue">The previous value of the property.</param>  
            /// <param name="newValue">The new value of the property.</param>  
            protected virtual void OnDefaultNamespaceChanged(  
                string oldValue, string newValue)  
            {  
                // Use the helper class to notify all of the elements in the model  
                // that the default namespace has changed.  
                TrackingHelper.UpdateTrackingCollectionProperty(  
                    this.Store,  
                    this.Elements,  
                    ExampleElement.NamespaceDomainPropertyId,  
                    ExampleElement.IsNamespaceTrackingDomainPropertyId);  
            }  
  
            // Update the change handler for the DefaultNamespace property.  
            internal sealed partial class DefaultNamespacePropertyHandler  
            {  
                /// <summary>Called when the DefaultNamespace property changes.</summary>  
                /// <param name="element">The model element that has the property that  
                /// changed.</param>  
                /// <param name="oldValue">The previous value of the property.</param>  
                /// <param name="newValue">The new value of the property.</param>  
                protected override void OnValueChanged(  
                    ExampleModel element, string oldValue, string newValue)  
                {  
                    base.OnValueChanged(element, oldValue, newValue);  
  
                    if (!element.Store.InUndoRedoOrRollback)  
                    {  
                        element.OnDefaultNamespaceChanged(oldValue, newValue);  
                    }  
                }  
            }  
  
            #endregion  
        }  
    }  
    ```  
  
## <a name="adding-custom-code-for-the-tracking-property"></a>Přidání vlastního kódu pro vlastnost sledování  
 Přidat `CalculateNamespace` metodu `ExampleElement` třída domény.  
  
 Definování tato metoda poskytuje logiku pro vlastnost CustomElements vypočítat `ExampleModel`. Tato metoda vrátí počet `ExampleElement` domény tříd, které mají Namespace, sledování vlastnost, která je v aktualizaci ve stavu uživatele a vrátí řetězec, který představuje tento počet jako podíl celkový počet elementů v modelu.  
  
 Také přidejte úložiště pro a metody k získání a nastavení, vlastnost vlastní úložiště Namespace `ExampleElement` třída domény.  
  
> [!NOTE]
>  Kód, který nástroje DSL generovat pro `ExampleModel` volání get a nastavte metody; však nástroje DSL nevydávají kód, který implementuje metody.  
  
#### <a name="to-add-the-method-for-the-custom-type-descriptor"></a>Chcete-li přidat metodu pro popisovače vlastního typu  
  
1.  Přidejte následující kód do souboru NamespaceTrackingProperty.cs.  
  
    ```csharp  
    using System;  
    using Microsoft.VisualStudio.Modeling;  
  
    namespace CompanyName.ProductName.TrackingPropertyDSL  
    {  
        // To the domain class that has the tracking property, add the caluclation  
        // for when the property is tracking.  
        public partial class ExampleElement  
        {  
            /// <summary>Calculates the actual value of the property when it is  
            /// tracking.</summary>  
            /// <returns>The value of the tracking property when it is  
            /// tracking.</returns>  
            /// <remarks>Making this method virtual allows child classes to modify  
            /// the calculation. This method does not need to perform validation, as  
            /// its caller handles validation prior to calling this method.  
            /// <para>In this case, the tracking value depends on the default namespace  
            /// property of the parent model.</para></remarks>  
            protected virtual string CalculateNamespace()  
            {  
                return this.ExampleModel.DefaultNamespace;  
            }  
  
            #region Tracking property implementation  
  
            // Implement the Namespace domain property of the ExampleElement domain class,  
            // and update the IsNamespaceTracking domain property value handler.  
  
            /// <summary>Storage for the Namespace property.</summary>  
            private string namespaceStorage;  
  
            /// <summary>Gets the value of the Namespace property.</summary>  
            /// <returns>The value of the Namespace property.</returns>  
            private string GetNamespaceValue()  
            {  
                // Only retrieve the tracked value if the store is not in the  
                // middle of a serialization transaction.  
                bool loading = this.Store.TransactionManager.InTransaction  
                    && this.Store.TransactionManager.CurrentTransaction.IsSerializing;  
  
                if (!loading && this.IsNamespaceTracking)  
                {  
                    try  
                    {  
                        return this.CalculateNamespace();  
                    }  
                    catch (NullReferenceException)  
                    {  
                        return default(string);  
                    }  
                    catch (Exception e)  
                    {  
                        if (CriticalException.IsCriticalException(e))  
                        {  
                            throw;  
                        }  
                        else  
                        {  
                            return default(string);  
                        }  
                    }  
                }  
  
                return namespaceStorage;  
            }  
  
            /// <summary>Sets the value of the Namespace property.</summary>  
            /// <param name="value">The new value for the property.</param>  
            private void SetNamespaceValue(string value)  
            {  
                namespaceStorage = value;  
  
                // Only update the state of the tracking property if the store is  
                // not in the middle of a serialization transaction.  
                bool loading = this.Store.TransactionManager.InTransaction  
                    && this.Store.TransactionManager.CurrentTransaction.IsSerializing;  
  
                if (!this.Store.InUndoRedoOrRollback && !loading)  
                {  
                    this.IsNamespaceTracking = false;  
                }  
            }  
  
            // Update the default behavior of the ExampleElement.IsNamespaceTracking  
            // domain property value handler.  
            internal sealed partial class IsNamespaceTrackingPropertyHandler  
            {  
                /// <summary>Called after the IsNamespaceTracking property changes.  
                /// </summary>  
                /// <param name="element">The model element that has the property  
                /// that changed.</param>  
                /// <param name="oldValue">The previous value of the property.  
                /// </param>  
                /// <param name="newValue">The new value of the property.</param>  
                protected override void OnValueChanged(  
                    ExampleElement element, Boolean oldValue, Boolean newValue)  
                {  
                    base.OnValueChanged(element, oldValue, newValue);  
                    if (!element.Store.InUndoRedoOrRollback && newValue)  
                    {  
                        DomainPropertyInfo propInfo =  
                            element.Store.DomainDataDirectory.GetDomainProperty(  
                                ExampleElement.NamespaceDomainPropertyId);  
                        propInfo.NotifyValueChange(element);  
                    }  
                }  
  
                /// <summary>Performs the reset operation for the IsNamespaceTracking  
                /// property for a model element.</summary>  
                /// <param name="element">The model element that has the property  
                /// to reset.</param>  
                internal void ResetValue(ExampleElement element)  
                {  
                    object calculatedValue = null;  
  
                    try  
                    {  
                        calculatedValue = element.CalculateNamespace();  
                    }  
                    catch (NullReferenceException)  
                    {  
                    }  
                    catch (System.Exception e)  
                    {  
                        if (CriticalException.IsCriticalException(e))  
                        {  
                            throw;  
                        }  
                    }  
  
                    if ((calculatedValue != null  
                        && object.Equals(element.Namespace, calculatedValue)))  
                    {  
                        element.isNamespaceTrackingPropertyStorage = true;  
                    }  
                }  
  
                /// <summary>Method to set IsNamespaceTracking to false so that this  
                /// instance of this tracking property is not storage-based.  
                /// </summary>  
                /// <param name="element">The element on which to reset the property  
                /// value.</param>  
                internal void PreResetValue(ExampleElement element)  
                {  
                    // Force the IsNamespaceTracking property to false so that the value  
                    // of the Namespace property is retrieved from storage.  
                    element.isNamespaceTrackingPropertyStorage = false;  
                }  
            }  
  
            #endregion  
        }  
    }  
    ```  
  
## <a name="adding-custom-code-to-support-serialization"></a>Přidání vlastního kódu pro podporu serializace  
 Přidáte kód pro podporu vlastních chování po zatížení pro serializaci XML.  
  
> [!NOTE]
>  Kód, že nástroje DSL generovat volání `OnPostLoadModel` a `OnPostLoadModelAndDiagram` metody; však nástroje DSL nevydávají kód, který implementuje tyto metody.  
  
#### <a name="to-add-code-to-support-the-custom-post-load-behavior"></a>Chcete-li přidat kód pro podporu vlastních chování po zatížení  
  
1.  Přidejte následující kód do souboru Serialization.cs.  
  
    ```csharp  
    using System;  
    using System.Diagnostics;  
    using Microsoft.VisualStudio.Modeling;  
  
    namespace CompanyName.ProductName.TrackingPropertyDSL  
    {  
        #region Helper classes for maintaining state while the store is serializing.  
  
        public abstract partial class TrackingPropertyDSLSerializationHelperBase  
        {  
            /// <summary>Reset the tracking state properties to their natural values  
            /// based on comparing storage with calculation.</summary>  
            /// <param name="store">The store that contains this model.</param>  
            internal static void ResetTrackingProperties(Store store)  
            {  
                // Two passes required - one to set all elements to storage-based  
                // then another to set some back to being tracking.  
                foreach (ModelElement element in store.ElementDirectory.AllElements)  
                {  
                    ExampleElement myElementInstance = element as ExampleElement;  
                    if (myElementInstance != null)  
                    {  
                        myElementInstance.PreResetIsTrackingProperties();  
                        continue;  
                    }  
                }  
                foreach (ModelElement element in store.ElementDirectory.AllElements)  
                {  
                    ExampleElement myElementInstance = element as ExampleElement;  
                    if (myElementInstance != null)  
                    {  
                        myElementInstance.ResetIsTrackingProperties();  
                        continue;  
                    }  
                }  
            }  
        }  
  
        // Add the pre-reset and reset methods for the model element.  
        public partial class ExampleElement  
        {  
            /// <summary>Calls the pre-reset method on the associated property value  
            /// handler for each tracking property of this model element.</summary>  
            internal virtual void PreResetIsTrackingProperties()  
            {  
                ExampleElement.IsNamespaceTrackingPropertyHandler.Instance.PreResetValue(this);  
            }  
  
            /// <summary>Calls the reset method on the associated property value  
            /// handler for each tracking property of this model element.</summary>  
            internal virtual void ResetIsTrackingProperties()  
            {  
                ExampleElement.IsNamespaceTrackingPropertyHandler.Instance.ResetValue(this);  
            }  
        }  
  
        #endregion  
  
        #region Custom serialization code  
  
        // To the serialization helper for the TrackingPropertyDSL class, add post  
        // load handlers to bind the tracking property to the serialization process.  
        // These handlers manage the tracking states and property values when the  
        // model is serialized and deserialized.  
        public partial class TrackingPropertyDSLSerializationHelperBase  
        {  
            /// <summary>Customize model loading.</summary>  
            /// <param name="serializationResult">The serialization result from the  
            /// load operation.</param>  
            /// <param name="partition">The partition in which the new  
            /// instance was created.</param>  
            /// <param name="fileName">The name of the file from which the  
            /// instance was deserialized.</param>  
            /// <param name="modelRoot">The root of the file that was loaded.  
            /// </param>  
            private void OnPostLoadModel(  
                SerializationResult serializationResult,  
                Partition partition,  
                string fileName,  
                ExampleModel modelRoot)  
            {  
            }  
  
            /// <summary>Customize model and diagram loading.</summary>  
            /// <param name="serializationResult">Stores serialization result from  
            /// the load operation.</param>  
            /// <param name="modelPartition">Partition in which the new  
            /// instance will be created.</param>  
            /// <param name="modelFileName">Name of the file from which the  
            /// instance will be deserialized.</param>  
            /// <param name="diagramPartition">Partition in which the new  
            /// diagram instance will be created.</param>  
            /// <param name="diagramFileName">Name of the file from which the  
            /// diagram instance will be deserialized.</param>  
            /// <param name="modelRoot">The root of the file that was loaded.</param>  
            /// <param name="diagram">The diagram matching the modelRoot.</param>  
            private void OnPostLoadModelAndDiagram(  
                SerializationResult serializationResult,  
                Partition modelPartition,  
                string modelFileName,  
                Partition diagramPartition,  
                string diagramFileName,  
                ExampleModel modelRoot,  
                TrackingPropertyDSLDiagram diagram)  
            {  
                Debug.Assert(modelPartition != null);  
                Debug.Assert(modelPartition.Store != null);  
  
                // Tracking properties need to be set up according to whether the  
                // serialization matches the calculated values.  
                TrackingPropertyDSLSerializationHelperBase.ResetTrackingProperties(  
                    modelPartition.Store);  
            }  
        }  
  
        #endregion  
    }  
    ```  
  
## <a name="testing-the-language"></a>Testování jazyk  
 Dalším krokem je sestavení a spuštění návrháře DSL v novou instanci třídy [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] , aby mohli ověřit, zda vlastnost sledování pracuje správně.  
  
#### <a name="to-exercise-the-language"></a>Vykonávat jazyk  
  
1.  Na **sestavení** nabídky, klikněte na tlačítko **znovu sestavit řešení**.  
  
2.  Na **ladění** nabídky, klikněte na tlačítko **spustit ladění**.  
  
     Experimentální sestavení [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] otevře **ladění** řešení, která obsahuje soubor prázdný testu.  
  
3.  V **Průzkumníku**, poklikejte na soubor Test.trackingPropertyDsl otevřít v návrháři a pak klikněte na návrhovou plochu.  
  
     Všimněte si, že v **vlastnosti** okna pro diagramu je vidět, **výchozí Namespace** vlastnost je **DefaultNamespace**a **vlastní elementy** vlastnost je **0/0**.  
  
4.  Přetáhněte **ExampleElement** element z **sada nástrojů** na povrch diagramu.  
  
5.  V **vlastnosti** okna pro element, vyberte **Element Namespace** vlastnost a změňte hodnotu z **DefaultNamespace** k  **OtherNamespace**.  
  
     Všimněte si, že hodnota **Element Namespace** je nyní zobrazeny tučně.  
  
6.  V **vlastnosti** okna, klikněte pravým tlačítkem na **Element Namespace**a potom klikněte na **resetovat**.  
  
     Hodnota vlastnosti byla změněna na **DefaultNamespace**, a hodnota je zobrazen v pravidelných písmo.  
  
     Klikněte pravým tlačítkem na **Element Namespace** znovu. **Resetovat** příkaz je nyní zakázán, protože vlastnost je aktuálně ve svém sledování stavu.  
  
7.  Přetáhněte další **ExampleElement** z **sada nástrojů** diagram prostor a změnit jeho **Element Namespace** k **OtherNamespace**.  
  
8.  Klikněte na návrhovou plochu.  
  
     V **vlastnosti** okna pro diagramu je vidět, hodnota **vlastní elementy** je nyní **1/2**.  
  
9. Změna **výchozí Namespace** pro diagram z **DefaultNamespace** k **NewNamespace**.  
  
     **Namespace** z první sleduje element **výchozí Namespace** vlastnost, zatímco **Namespace** druhého element uchovává hodnotu jehouživatelaktualizoval **OtherNamespace**.  
  
10. Uložte řešení a pak zavřete experimentální sestavení.  
  
## <a name="next-steps"></a>Další kroky  
 Pokud máte v plánu používat více než jeden sledování vlastnost, nebo implementovat vlastnosti sledování ve více než jeden DSL, můžete vytvořit šablonu text k vygenerování společný kód pro každou vlastnost sledování podporu. Další informace o textové šablony najdete v tématu [generování kódu a textové šablony T4](../modeling/code-generation-and-t4-text-templates.md).  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Modeling.Design.TrackingPropertyDescriptor>   
 <xref:Microsoft.VisualStudio.Modeling.Design.ElementTypeDescriptor>   
 [Jak definovat jazyka domény](../modeling/how-to-define-a-domain-specific-language.md)   
 [Postupy: vytvoření řešení jazyka domény](../modeling/how-to-create-a-domain-specific-language-solution.md)   
