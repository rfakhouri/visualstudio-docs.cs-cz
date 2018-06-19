---
title: Vizualizace a zobrazení dat | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], viewing data
- debugging [Debugging SDK], visualizing data
ms.assetid: 699dd0f5-7569-40b3-ade6-d0fe53e832bc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ebaa07c8fe70e1842334b0bf7c28eb7491fd9c44
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31132479"
---
# <a name="visualizing-and-viewing-data"></a>Vizualizace a zobrazení dat
Zadejte vizualizérech a zobrazení dat vlastní prohlížeče způsobem, který je rychle smysl vývojář. Vyhodnocení výrazu (EE) může podporovat vizualizérech typ třetích stran, stejně jako zadat vlastní vlastní prohlížeče.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Určuje, kolik typ vizualizérech a vlastní prohlížeče jsou spojeny s typu objektu voláním [GetCustomViewerCount](../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md) metoda. Pokud je alespoň jeden typ vizualizér nebo vlastní prohlížeč k dispozici, Visual Studio zavolá [GetCustomViewerList](../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) metoda pro načtení seznamu těchto vizualizérech a prohlížeče (ve skutečnosti, seznam `CLSID`s, který implementovat vizualizérech a prohlížeče) a k jejich zobrazení pro uživatele.  
  
## <a name="supporting-type-visualizers"></a>Podpora typ Vizualizérech  
 Existuje několik rozhraní, která EE musí implementovat pro podporu vizualizérech typu. Tato rozhraní můžete rozdělit na dvě rozsáhlé kategorie: ty, které seznamu vizualizérech typu a ty, které přístup k datům vlastnost.  
  
### <a name="listing-type-visualizers"></a>Výpis typu Vizualizérech  
 EE podporuje výpis typu vizualizérech při implementaci `IDebugProperty3::GetCustomViewerCount` a `IDebugProperty3::GetCustomViewerList`. Tyto metody předá pro odpovídající metody [GetCustomViewerCount](../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewercount.md) a [GetCustomViewerList](../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md).  
  
 [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md) se získá voláním [CreateVisualizerService](../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md). Tato metoda vyžaduje, [IDebugBinder3](../../extensibility/debugger/reference/idebugbinder3.md) rozhraní, které se získávají z [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md) rozhraní předaný [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md). `IEEVisualizerServiceProvider::CreateVisualizerService` také vyžaduje [IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md) a [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md) rozhraní, které byly předány `IDebugParsedExpression::EvaluateSync`. Rozhraní konečné potřebné pro vytvoření `IEEVisualizerService` rozhraní je [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md) rozhraní, která implementuje EE. Toto rozhraní umožňuje provedení vlastnosti se vizualizována změn. Všechna data vlastnost je zapouzdřené v [IDebugObject](../../extensibility/debugger/reference/idebugobject.md) rozhraní, což je také implementované EE.  
  
### <a name="accessing-property-data"></a>Přístup k datům vlastnost  
 Přístup k datům vlastnost se provádí prostřednictvím [IPropertyProxyEESide](../../extensibility/debugger/reference/ipropertyproxyeeside.md) rozhraní. Pro získání toto rozhraní, Visual Studio volá [QueryInterface](/cpp/atl/queryinterface) vlastnost objektu získat [IPropertyProxyProvider](../../extensibility/debugger/reference/ipropertyproxyprovider.md) rozhraní (implementována pro stejný objekt, který implementuje [ IDebugProperty3](../../extensibility/debugger/reference/idebugproperty3.md) rozhraní) a potom zavolá [GetPropertyProxy](../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md) metoda získat `IPropertyProxyEESide` rozhraní.  
  
 Všechna data předaná do a z `IPropertyProxyEESide` rozhraní je zapouzdřené v [IEEDataStorage](../../extensibility/debugger/reference/ieedatastorage.md) rozhraní. Toto rozhraní představuje pole bajtů a je implementováno modulem Visual Studio a EE. Když jsou data vlastnosti chcete změnit, Visual Studio vytvoří `IEEDataStorage` objektu, která uchovává nová data a volání [CreateReplacementObject](../../extensibility/debugger/reference/ipropertyproxyeeside-createreplacementobject.md) s tímto objektem data, aby bylo možné získat novou `IEEDataStorage` objekt, který je zase, Předaný [InPlaceUpdateObject](../../extensibility/debugger/reference/ipropertyproxyeeside-inplaceupdateobject.md) aktualizace dat vlastnosti. `IPropertyProxyEESide::CreateReplacementObject` Umožňuje EE instance vlastní třídy, který implementuje `IEEDataStorage` rozhraní.  
  
## <a name="supporting-custom-viewers"></a>Podpora vlastních prohlížečů  
 Příznak `DBG_ATTRIB_VALUE_CUSTOM_VIEWER` je nastavena v `dwAttrib` pole z [DEBUG_PROPERTY_INFO](../../extensibility/debugger/reference/debug-property-info.md) struktury (vrácený volání [GetPropertyInfo –](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)) k označení, že objekt obsahuje vlastní prohlížeč přidružené s ním. Pokud je tento příznak nastaven, získá sady Visual Studio [IDebugProperty3](../../extensibility/debugger/reference/idebugproperty3.md) rozhraní z [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) rozhraní pomocí [QueryInterface](/cpp/atl/queryinterface).  
  
 Pokud uživatel vybere vlastní prohlížeč, Visual Studio vytvoří vlastní prohlížeč pomocí v prohlížeči `CLSID` poskytl `IDebugProperty3::GetCustomViewerList` metoda. Visual Studio pak zavolá [položky DisplayValue](../../extensibility/debugger/reference/idebugcustomviewer-displayvalue.md) zobrazíte hodnotu pro uživatele.  
  
 Za normálních okolností `IDebugCustomViewer::DisplayValue` uvede dat zobrazení jen pro čtení. Povolit změny dat, musí EE implementovat vlastní rozhraní, které podporuje u vlastnosti objektu se měnícími se daty. `IDebugCustomViewer::DisplayValue` Metoda používá toto vlastní rozhraní pro podporu Změna data. Metoda hledá vlastní rozhraní na `IDebugProperty2` rozhraní předaná jako `pDebugProperty` argument.  
  
## <a name="supporting-both-type-visualizers-and-custom-viewers"></a>Podpora obě zadejte Vizualizérech a vlastní prohlížečů  
 EE může podporovat typ vizualizérech i vlastní prohlížečů v [GetCustomViewerCount](../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md) a [GetCustomViewerList](../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) metody. Nejprve EE přidá počet vlastní prohlížečů, které je poskytnutí hodnoty vrácené [GetCustomViewerCount](../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewercount.md) metoda. Druhý, EE připojí `CLSID`s vlastním vlastní prohlížeče do seznamu vrácených [GetCustomViewerList](../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [Ladění úlohy](../../extensibility/debugger/debugging-tasks.md)   
 [Vizualizér typů a vlastní prohlížeč](../../extensibility/debugger/type-visualizer-and-custom-viewer.md)