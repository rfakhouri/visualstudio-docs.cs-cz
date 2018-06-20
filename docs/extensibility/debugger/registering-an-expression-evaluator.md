---
title: Registrace vyhodnocení výrazu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluators, registering
ms.assetid: 236be234-e05f-4ad8-9200-24ce51768ecf
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b3e764220fe5fe01e20b66af403dfd8b423e34e7
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/19/2018
ms.locfileid: "36234023"
---
# <a name="registering-an-expression-evaluator"></a>Registrace vyhodnocovače výrazů
> [!IMPORTANT]
>  V sadě Visual Studio 2015 se již nepoužívá tímto způsobem implementace vyhodnocovače výrazů. Informace o implementaci vyhodnocovače výrazů CLR, najdete v tématu [vyhodnocovače výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Vyhodnocení výrazu (EE) musí se registrovat jako objekt pro vytváření třídy pomocí prostředí Windows COM i v sadě Visual Studio. EE je implementovaný jako knihovny DLL tak, aby ho může vloženy do adresního prostoru ladění modulu (DE) nebo sady Visual Studio adresního prostoru, podle toho, která vytvoří instanci entity EE.  
  
## <a name="managed-code-expression-evaluator"></a>Vyhodnocovací filtr výrazů spravovaného kódu  
 Spravovaný kód EE je implementovaný jako knihovny tříd, což je knihovna DLL, která registruje COM prostředí, obvykle spouštěné volání VSIP program **regpkg.exe**. Samotný proces zápisu klíče registru pro prostředí COM se proto automaticky.  
  
 Metoda hlavní třídy je označena <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute>, což indikuje, že metoda má být volána, když knihovnu DLL registrované s COM. Tato metoda registrace často říká `RegisterClass`, provede úlohu registrace knihovny DLL pomocí sady Visual Studio. Odpovídající `UnregisterClass` (označené jako <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute>), vrátí zpět důsledky `RegisterClass` při odinstalaci knihovnu DLL.  
  
 Stejné položky registru jsou vytvářeny jako EE napsané v nespravovaný kód. jediným rozdílem je, že neexistuje žádná pomocné funkce, jako `SetEEMetric` které udělají tuto práci za vás. Příkladem tohoto procesu registrace nebo odregistrace vypadá takto:  
  
### <a name="example"></a>Příklad  
 Tato funkce se popisuje, jak spravovaného kódu EE zaregistruje a sám zruší registraci pomocí sady Visual Studio.  
  
```csharp  
namespace EEMC  
{  
    [GuidAttribute("462D4A3D-B257-4AEE-97CD-5918C7531757")]  
    public class EEMCClass : IDebugExpressionEvaluator  
    {  
        #region Register and unregister.  
        private static Guid guidMycLang = new Guid("462D4A3E-B257-4AEE-97CD-5918C7531757");  
        private static string languageName = "MyC";  
        private static string eeName = "MyC Expression Evaluator";  
  
        private static Guid guidMicrosoftVendor = new Guid("994B45C4-E6E9-11D2-903F-00C04FA302A1");  
        private static Guid guidCOMPlusOnlyEng = new Guid("449EC4CC-30D2-4032-9256-EE18EB41B62B");  
        private static Guid guidCOMPlusNativeEng = new Guid("92EF0900-2251-11D2-B72E-0000F87572EF");  
  
        /// <summary>  
        /// Register the expression evaluator.  
        /// Set "project properties/configuration properties/build/register for COM interop" to true.  
        /// </summary>  
         [ComRegisterFunctionAttribute]  
        public static void RegisterClass(Type t)  
        {  
            // Get Visual Studio version (set by regpkg.exe)  
            string hive = Environment.GetEnvironmentVariable("EnvSdk_RegKey");  
            string s = @"SOFTWARE\Microsoft\VisualStudio\"  
                        + hive  
                        + @"\AD7Metrics\ExpressionEvaluator";  
  
            RegistryKey rk = Registry.LocalMachine.CreateSubKey(s);  
            if (rk == null)  return;  
  
            rk = rk.CreateSubKey(guidMycLang.ToString("B"));  
            rk = rk.CreateSubKey(guidMicrosoftVendor.ToString("B"));  
            rk.SetValue("CLSID", t.GUID.ToString("B"));  
            rk.SetValue("Language", languageName);  
            rk.SetValue("Name", eeName);  
  
            rk = rk.CreateSubKey("Engine");  
            rk.SetValue("0", guidCOMPlusOnlyEng.ToString("B"));  
            rk.SetValue("1", guidCOMPlusNativeEng.ToString("B"));  
        }  
        /// <summary>  
        /// Unregister the expression evaluator.  
        /// </summary>  
         [ComUnregisterFunctionAttribute]  
        public static void UnregisterClass(Type t)  
        {  
            // Get Visual Studio version (set by regpkg.exe)  
            string hive = Environment.GetEnvironmentVariable("EnvSdk_RegKey");  
            string s = @"SOFTWARE\Microsoft\VisualStudio\"  
                        + hive  
                        + @"\AD7Metrics\ExpressionEvaluator\"  
                        + guidMycLang.ToString("B");  
            RegistryKey key = Registry.LocalMachine.OpenSubKey(s);  
            if (key != null)  
            {  
                key.Close();  
                Registry.LocalMachine.DeleteSubKeyTree(s);  
            }  
        }  
    }  
}  
```  
  
## <a name="unmanaged-code-expression-evaluator"></a>Vyhodnocovací filtr výrazů nespravovaného kódu  
 Knihovny DLL EE implementuje `DllRegisterServer` funkce k registraci v prostředí COM, jakož i Visual Studio.  
  
> [!NOTE]
>  Kód MyCEE ukázkový kód registru naleznete v souboru dllentry.cpp, který je umístěný v instalaci VSIP pod EnVSDK\MyCPkgs\MyCEE.  
  
### <a name="dll-server-process"></a>Proces serveru knihovny DLL  
 Při registraci EE, serveru knihovny DLL:  
  
1.  Zaregistruje její zdroj tříd `CLSID` souladu s konvencemi normální COM.  
  
2.  Volání pomocné funkce `SetEEMetric` k registraci pomocí sady Visual Studio EE metriky zobrazené v následující tabulce. Funkce `SetEEMetric` a metriky níže uvedené jsou součástí knihovny dbgmetric.lib. V tématu [SDK pomocníci pro ladění](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) podrobnosti.  
  
    |Metrika|Popis|  
    |------------|-----------------|  
    |`metricCLSID`|`CLSID` objektu pro vytváření EE – třída|  
    |`metricName`|Název EE jako zobrazitelné řetězec|  
    |`metricLanguage`|Název jazyka, který je EE určená k vyhodnocení|  
    |`metricEngine`|`GUID`s moduly ladění (DE), které pracují se tento EE|  
  
    > [!NOTE]
    >  `metricLanguage``GUID` Identifikuje jazyk podle názvu, ale je `guidLang` argument `SetEEMetric` , vybere jazyk. Pokud kompilátor vygeneruje soubor s informacemi o ladění, musí být uveden příslušný `guidLang` , aby je DE věděla, které EE používat. DE obvykle požádá zprostředkovatele symbol pro tento jazyk `GUID`, který je uložený v souboru informace ladění.  
  
3.  Zaregistruje pomocí sady Visual Studio vytvořením klíče v části HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\\*X.Y*, kde *X.Y* je verze sady Visual Studio k registraci.  
  
### <a name="example"></a>Příklad  
 Tato funkce se popisuje, jak nespravovaného kódu (C++) EE zaregistruje a sám zruší registraci pomocí sady Visual Studio.  
  
```cpp  
/*---------------------------------------------------------  
  Registration  
-----------------------------------------------------------*/  
#ifndef LREGKEY_VISUALSTUDIOROOT  
    #define LREGKEY_VISUALSTUDIOROOT L"Software\\Microsoft\\VisualStudio\\8.0"  
#endif  
  
static HRESULT RegisterMetric( bool registerIt )  
{  
    // check where we should register  
    const ULONG cchBuffer = _MAX_PATH;  
    WCHAR wszRegistrationRoot[cchBuffer];  
    DWORD cchFreeBuffer = cchBuffer - 1;  
    wcscpy(wszRegistrationRoot, LREGKEY_VISUALSTUDIOROOT_NOVERSION);  
    wcscat(wszRegistrationRoot, L"\\");  
  
    // this is Environment SDK specific  
    // we check for  EnvSdk_RegKey environment variable to  
    // determine where to register  
    DWORD cchDefRegRoot = lstrlenW(LREGKEY_VISUALSTUDIOROOT_NOVERSION) + 1;  
    cchFreeBuffer = cchFreeBuffer - cchDefRegRoot;  
    DWORD cchEnvVarRead = GetEnvironmentVariableW(  
        /* LPCTSTR */ L"EnvSdk_RegKey", // environment variable name  
        /* LPTSTR  */ &wszRegistrationRoot[cchDefRegRoot],// buffer for variable value  
        /* DWORD   */ cchFreeBuffer);// size of buffer  
    if (cchEnvVarRead >= cchFreeBuffer)  
        return E_UNEXPECTED;  
    // If the environment variable does not exist then we must use   
    // LREGKEY_VISUALSTUDIOROOT which has the version number.  
    if (0 == cchEnvVarRead)  
        wcscpy(wszRegistrationRoot, LREGKEY_VISUALSTUDIOROOT);  
  
    if (registerIt)  
    {  
        SetEEMetric(guidMycLang,  
                    guidMicrosoftVendor,  
                    metricCLSID,  
                    CLSID_MycEE,  
                    wszRegistrationRoot );  
        SetEEMetric(guidMycLang,  
                    guidMicrosoftVendor,  
                    metricName,  
                    GetString(IDS_INFO_MYCDESCRIPTION),  
                    wszRegistrationRoot );  
        SetEEMetric(guidMycLang,  
                    guidMicrosoftVendor,  
                    metricLanguage, L"MyC",  
                    wszRegistrationRoot);  
  
        GUID engineGuids[2];  
        engineGuids[0] = guidCOMPlusOnlyEng;  
        engineGuids[1] = guidCOMPlusNativeEng;  
        SetEEMetric(guidMycLang,  
                    guidMicrosoftVendor,  
                    metricEngine,  
                    engineGuids,  
                    2,  
                    wszRegistrationRoot);  
    }  
    else  
    {  
        RemoveEEMetric( guidMycLang,  
                        guidMicrosoftVendor,  
                        metricCLSID,  
                        wszRegistrationRoot);  
        RemoveEEMetric( guidMycLang,  
                        guidMicrosoftVendor,  
                        metricName,  
                        wszRegistrationRoot );  
        RemoveEEMetric( guidMycLang,  
                        guidMicrosoftVendor,  
                        metricLanguage,  
                        wszRegistrationRoot );  
        RemoveEEMetric( guidMycLang,  
                        guidMicrosoftVendor,  
                        metricEngine,  
                        wszRegistrationRoot );  
    }  
  
    return S_OK;  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Zápis vyhodnocovací filtr výrazů CLR](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)   
 [Pomocníci sad SDK pro ladění](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)
