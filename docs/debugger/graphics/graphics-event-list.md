---
title: Seznam událostí grafiky | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.graphics.eventlist
ms.assetid: a1252e19-b27d-4dc7-a16b-fdac894c1f0e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b3640a1bbb06de7b05eeb62f847504690921b324
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="graphics-event-list"></a>Seznam událostí grafiky
Použijte seznam událostí grafiky ve Visual Studio Graphics Analyzer prozkoumat Direct3D – události, které nebyly zaznamenány při vykreslování rámce hry nebo aplikace.  
  
 Toto je seznam událostí:  
  
 ![Seznam událostí, které mají "Index" v názvu. ] (media/gfx_diag_demo_event_list_orientation.png "gfx_diag_demo_event_list_orientation")  
  
## <a name="using-the-event-list"></a>Pomocí seznamu těchto událostí  
 Když vyberete událost v případě, že seznamu, se projeví v informace, které se zobrazí v jiných nástrojích analýza grafických; Pomocí seznamu těchto událostí ve vzájemné součinnosti tyto nástroje můžete prozkoumat problém vykreslování podrobně zjistit jeho příčinu. Další informace o tom, jak můžete řešení problémů vykreslování pomocí seznamu těchto událostí společně s další analýza grafických nástrojů najdete v tématu [příklady](graphics-diagnostics-examples.md).  
  
 Efektivním použitím funkce seznamu těchto událostí je důležité pro získání kolem komplexní rámců, které může obsahovat tisíce události. Efektivně používat seznamu těchto událostí, zvolte že zobrazení vám nejvíce vyhovuje, použijte funkci vyhledávání Pokud chcete filtrovat seznam událostí, postupujte podle odkazy na další informace o Direct3D – objekty, které jsou přidružené události a použijte šipku tlačítka pro přesun mezi rychle zakreslit volání.  
  
### <a name="color-coded-events-in-direct3d-12"></a>Barevně události v Direct3D – 12  
 Direct3D – 12 zpřístupní více front, které odpovídají na jiný hardware funkčnost. K identifikaci fronty, který je spojen s konkrétní grafiky událost v Direct3D – 12 události jsou rozlišené barevně v seznamu těchto událostí podle jejich fronty, při práci s zachycení Direct3D – 12 aplikace.  
  
|Direct3D – 12 fronty|Barva|  
|-----------------------|-----------|  
|Vykreslení fronty|zelená|  
|Výpočetní fronty|žlutý|  
|Zkopírujte fronty|oranžová|  
  
 Direct3D – 11 není vystavit více front, takže události nejsou barevně v seznamu událostí při práci s zachycení aplikace Direct3D – 11.  
  
### <a name="event-list-views"></a>Zobrazení seznamu událostí  
 Seznam událostí podporuje dvě různá zobrazení, které umožňují uspořádat událostí grafiky různými způsoby pro podporu vašeho pracovního postupu a předvolby. První zobrazení *GPU fungovat zobrazení* který organizuje hierarchicky událostí a jejich přidružené stavu. Druhý zobrazení je *časová osa zobrazení* který slouží k uspořádání události časovém pořadí jako plochý seznam.  
  
 **GPU pracovní** zobrazení  
 Zobrazí zachycení událostí a jejich stavu v hierarchii. Nejvyšší úrovni hierarchie se skládá z události, například volání kreslení, zruší, přítomen a týkající se zobrazení. V seznamu, můžete rozšířit událostí kreslení volání k zobrazení stavu zařízení, která byla aktuální v době kreslení volání; a můžete dále rozšířit jednotlivé typy stav chcete zobrazit události, které nastavení jejich hodnot. Na této úrovni můžete také podívat, jestli konkrétní stav byl nastaven v předchozí snímek, nebo pokud nastavení více než jednou od poslední kreslení volání.  
  
 **Časová osa** zobrazení  
 Zobrazí všechny události zaznamenané v chronologickém pořadí. Tento způsob uspořádání seznamu těchto událostí je stejný jako předchozí verze sady Visual Studio.  
  
##### <a name="to-change-the-event-list-view-mode"></a>Chcete-li změnit režim zobrazení seznamu událostí  
  
-   V **seznam událostí grafiky** okno výše seznam událostí, vyhledejte **zobrazení** rozevíracího seznamu a zvolit buď **časová osa** zobrazení nebo **GPU pracovní** zobrazení.  
  
### <a name="filtering-events"></a>Filtrování událostí  
 Do vyhledávacího pole můžete použít – nachází v pravém horním rohu **seznam událostí grafiky** okno – pro filtrování seznamu události zahrnout jenom události, jejichž názvy obsahují konkrétní klíčová slova. Můžete určit jeden klíčová slova jako `Vertex`– jak je vidět na předchozím obrázku – nebo více klíčová slova pomocí seznamu oddělený středníkem jako `Draw;Primitive`– který odpovídá události, které mají buď `Draw` nebo `Primitive` jejich názvy. Hledání jsou citlivé na prázdné – například `VSSet` a `VS Set` jsou různé hledání – proto zkontrolujte, zda formuláře hledání pečlivě.  
  
### <a name="moving-between-draw-calls"></a>Přesouvání mezi kreslení volání  
 Protože zkoumání `Draw` volání je obzvláště důležité, můžete použít **přejděte na další kreslení volání** a **přejít na předchozí kreslení volání** tlačítka – nachází v levém horním rohu **Seznam událostí grafiky** okno – k vyhledání a rychle přesouvat mezi kreslení volání.  
  
### <a name="links-to-graphics-objects"></a>Odkazy na grafických objektů  
 Pochopení určité události grafiky, budete pravděpodobně potřebovat další informace o aktuálním stavu Direct3D nebo o Direct3D – objekty, které odkazuje událost. Mnoho událostí obsahují odkazy na tyto informace, které můžete provést další podrobnosti.  
  
## <a name="kinds-of-events-and-event-markers"></a>Druhy značky události a události  
 Události, které se zobrazí v případě, že seznam jsou uspořádány do čtyř kategorií: Obecné události zakreslit značky uživatelem definované události, uživatelem definované události skupiny a události. S výjimkou obecné události zobrazí se společně s ikonu, která určuje kategorii, která patří do jednotlivých událostí.  
  
|Ikona|Popis události|  
|----------|-----------------------|  
|(bez ikony)|Obecné události<br /> Libovolnou událost, který není uživatelem definované události, uživatelem definované události skupiny nebo kreslení událostí.|  
|![Ikona událostí kreslení](media/vsg_eventlist_icon_draw.png "vsg_eventlist_icon_draw")|Draw – událost<br /> Označí kreslení událostí, které došlo v průběhu zaznamenané rámečku.|  
|![Uživatel&#45;definované ikonu značky událost](media/vsg_eventlist_icon_user.png "vsg_eventlist_icon_user")|Uživatelem definované události skupiny<br /> Skupiny související události, jak jsou definovány pomocí aplikace.|  
|![Uživatel&#45;definované ikonu značky událost](media/vsg_eventlist_icon_user.png "vsg_eventlist_icon_user")|Uživatelem definované události značky<br /> Označuje konkrétní umístění, podle definice aplikace.|  
  
## <a name="marking-user-defined-events-in-your-app"></a>Označování událostí definovaných uživatelem v aplikaci  
 Uživatelem definované události jsou specifické pro vaši aplikaci. Můžete je používat ke korelaci významné události, které nastaly v aplikaci s událostmi v seznamu událostí grafiky. Například můžete vytvořit uživatelem definované události skupiny pro uspořádání související události, jako jsou ty, které vykreslení uživatelského rozhraní – do skupiny nebo hierarchie tak, aby můžete snadno procházet seznam událostí, nebo můžete vytvořit značky při druhy objektů jsou vykresluje, takže budete moci snadno najít, že jejich událostí grafiky v seznamu událostí.  
  
 Vytvoření skupin a značky ve vaší aplikaci, použijte stejná rozhraní API, která Direct3D – poskytuje pro použití v jiných Direct3D – nástroje pro ladění. Mezi verzemi Direct3D – někdy změnit tato rozhraní API, ale základní funkce je stejný.  
  
### <a name="user-defined-events-in-direct3d-12"></a>Uživatelem definované události v Direct3D – 12  
 Vytvoření skupin a značky v Direct3D – 12, pomocí rozhraní API popsané v této části. Následující tabulka shrnuje rozhraní API, který můžete použít v závislosti na tom, jestli jsou označení událostí ve frontě příkaz nebo příkaz seznamu.  
  
|Popis rozhraní API|[ID3D12CommandQueue](https://msdn.microsoft.com/library/dn788627.aspx)|[ID3D12GraphicsCommandList](https://msdn.microsoft.com/library/dn903537.aspx)|  
|---------------------|----------------------------------------------------------------------------|-----------------------------------------------------------------------------------|  
|Zkontrolovat dostupnost uživatelem definované události|[PIXGetStatus](http://msdn.microsoft.com/en-us/f7ebd985-fb5d-46d7-abec-099df4b9be0e)|[PIXGetStatus](http://msdn.microsoft.com/en-us/1046ac43-a0a3-42bf-bae8-14aa72fa7567)|  
|Začít skupinu událostí|[PIXBeginEvent](http://msdn.microsoft.com/en-us/5f51fff7-f313-4558-965b-2a443653cd7b)|[PIXBeginEvent](http://msdn.microsoft.com/en-us/4ddb3311-b9b5-449a-bbfb-7634e0d56e87)|  
|End skupině událostí|[PIXEndEvent](http://msdn.microsoft.com/en-us/fb526bf2-c17d-4a2a-8665-3b577a0f7fba)|[PIXEndEvent](http://msdn.microsoft.com/en-us/a3cd34a9-9dd9-40e1-ae86-0214b25ff185)|  
|Vytvoření značky událostí|[PIXSetMarker](http://msdn.microsoft.com/en-us/0caf49ed-c99d-405e-89f4-0c887b8474ad)|[PIXSetMarker](http://msdn.microsoft.com/en-us/6610e5b9-a0c5-4236-b551-b6eb9fac64c1)|  
  
### <a name="user-defined-events-in-direct3d-11-and-earlier"></a>Uživatelem definované události Direct3D – 11 a starší  
 Vytvoření skupin a značky Direct3D – 11 nebo dřívější, pomocí rozhraní API popsané v této části. Následující tabulka shrnuje rozhraní API, která můžete použít pro různé verze 11 Direct3D – a dřívějších verzích Direct3D.  
  
|Popis rozhraní API|[ID3D11DeviceContext2](http://msdn.microsoft.com/library/windows/desktop/dn280498.aspx) (Direct3D – 11.2)|[ID3DUserDefinedAnnotation](http://go.microsoft.com/fwlink/p/?LinkID=250967) (Direct3D – 11.1)|Rozhraní API D3DPerf_ rodiny (Direct3D 11.0 a starší)|  
|---------------------|---------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|--------------------------------------------------------|  
|Začít skupinu událostí|`BeginEventInt`|`BeginEvent`|`D3DPerf_BeginEvent`|  
|End skupině událostí|`EndEventInt`|`EndEvent`|`D3DPerf_EndEvent`|  
|Vytvoření značky událostí|`SetMarkerInt`|`SetMarker`|`D3DPerf_SetMarker`|  
  
 Můžete použít některou z těchto rozhraní API, které podporuje vaše verzi Direct3D – například, pokud cílíte na rozhraní API 11.1 Direct3D, můžete použít buď `SetMarker` nebo `D3DPerf_SetMarker` k vytvoření značky události, ale ne `SetMarkerInt` protože jeho k dispozici pouze v Direct3D – 11.2 – a dokonce je možné kombinovat ty, které společně podporují různé verze Direct3D – ve stejné aplikaci.  

<!-- VERSIONLESS -->
<a name="resource-history"></a>
## Visual Studio pro prostředek historie 2017 a větší obsahovat **historie prostředků** okno.  Výběr ikona sledování ![ikona sledování](media/gfx_watch.png) vedle záznamu v **seznam událostí** se otevře okno **historie prostředků** okno vidíte níže:

![Historie prostředků](media/gfx_diag_resource_history.png)

Toto okno umožňuje zobrazit historii vybranou položku v seznamu těchto událostí.  Rozevírací seznam v horní části lze zvolit další položky k zobrazení historie.  V horní polovině okno obsahuje **události instalace rámce**.  Toto jsou události, které spadají do *vytvořit* zadejte kategorie a jsou volání, které obvykle inicializují a vytvořit prostředek.  Dolní polovinu okno obsahuje **rámce události** části.  Tyto jsou normální číst a zapsat události, ke kterým dochází při používání prostředku.  

Sloupec|Popis
---|---
**Typ** | Zobrazuje typ položky obvykle *vytvořit*, *čtení* a *zápisu*.  
**Zobrazení** | Zobrazí Miniatura prostředku v daném časovém okamžiku.  Dvakrát klikněte na miniaturu otevření zobrazení Podrobnosti o prostředku v daném čase.  
**Události**| Volání metody, které došlo k chybě, která zobrazuje události vygenerované.  Všechny další historie na jednotlivé položky lze zobrazit výběrem ikony sledovat ![ikona sledování](media/gfx_watch.png) na příslušný řádek.  Navíc libovolnou položku, která se vykresluje v modrý text, například `m_commandList` na snímku obrazovky výše, lze vybrat další podrobnosti.
<!-- /VERSIONLESS -->

## <a name="see-also"></a>Viz také  
 [Návod: Chybějící objekty z důvodu stavu zařízení](walkthrough-missing-objects-due-to-device-state.md)