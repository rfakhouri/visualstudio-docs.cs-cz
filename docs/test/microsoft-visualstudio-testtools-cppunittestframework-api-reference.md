---
title: "Referenční dokumentace rozhraní API atributu Microsoft.VisualStudio.TestTools.CppUnitTestFramework | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: mblome
manager: ghogen
ms.workload: multiple
author: mikeblome
ms.openlocfilehash: 89829ba1c618f444268d7beae7c85332a49e6007
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2018
---
# <a name="microsoftvisualstudiotesttoolscppunittestframework-api-reference"></a>Referenční dokumentace rozhraní API atributu Microsoft.VisualStudio.TestTools.CppUnitTestFramework
Toto téma uvádí veřejné členy `Microsoft::VisualStudio::CppUnitTestFramework` oboru názvů. Použijte tato rozhraní API pro zápis testů částí C++ podle Microsoft nativní Unit Test Framework. Je [příklad použití](#example) na konci tohoto tématu. 
  
 Soubory hlaviček, které jsou umístěné v *VisualStudio2012 [x 86] InstallFolder***\VC\UnitTest\include** složky.  
  
 Soubory lib nacházejí v *VisualStudio2012 [x 86] InstallFolder***\VC\UnitTest\lib** složky.

Záhlaví a lib cesty se automaticky nakonfigurují v nativní testovacího projektu.  

  
##  <a name="In_this_topic"></a>V tomto tématu  
 [CppUnitTest.h](#cppUnitTest_h)  
  
-   [Vytvořit testovací třídy a metody](#create_test_classes_and_methods)  
  
-   [Inicializace a čištění](#Initialize_and_cleanup)  
  
    -   [Test metody](#test_methods)  
  
    -   [Test třídy](#test_classes)  
  
    -   [Test moduly](#test_modules)  
  
-   [Vytvořte atributy testu](#create_test_attributes)  
  
    -   [Atributy metody testu](#test_method_attributes)  
  
    -   [Atributy třídy testu](#test_class_attributes)  
  
    -   [Atributy modulu testu](#test_module_attributes)  
  
    -   [Předem definované atributy](#pre_defined_attributes)  
  
     [CppUnitTestAssert.h](#cppUnitTestAssert_h)  
  
    -   [Vyhodnotí obecné](#general_asserts)  
  
        -   [Jsou stejné](#general_are_equal)  
  
        -   [Nejsou stejné](#general_are_not_equal)  
  
        -   [Jsou stejné](#general_are_same)  
  
        -   [Nejsou stejné](#general_are_not_same)  
  
        -   [Má hodnotu Null.](#general_is_null)  
  
        -   [Nemá hodnotu Null](#general_is_not_null)  
  
        -   [Hodnotu True](#general_is_True)  
  
        -   [Je hodnota False](#general_is_false)  
  
        -   [Selhání](#general_Fail)  
  
    -   [Vyhodnotí prostředí Windows Runtime](#winrt_asserts)  
  
        -   [Jsou stejné](#winrt_are_equal)  
  
        -   [Jsou stejné](#winrt_are_same)  
  
        -   [Nejsou stejné](#winrt_are_not_equal)  
  
        -   [Nejsou stejné](#winrt_are_not_same)  
  
        -   [Má hodnotu Null.](#winrt_is_null)  
  
        -   [Nemá hodnotu Null](#winrt_is_not_null)  
  
    -   [Vyhodnotí výjimky](#exception_asserts)  
  
        -   [Očekávané výjimky](#expect_exception)  
  
         [CppUnitTestLogger.h](#cppunittestlogger_h)  
  
        -   [Protokoly](#logger)  
  
        -   [Zapsat zprávu](#write_message)  
    -    [Příklad použití](#example)
  
##  <a name="cppUnitTest_h"></a>CppUnitTest.h  
  
###  <a name="create_test_classes_and_methods"></a>Vytvořit testovací třídy a metody  
  
```cpp  
TEST_CLASS(className)  
```  
  
 Vyžaduje se pro každou třídu obsahující testovací metody. Identifikuje *className* jako třída test. `TEST_CLASS`musí být deklarován v namescape oboru.  
  
```cpp  
TEST_METHOD(methodName)   
{  
    // test method body  
}  
  
```  
  
 Definuje *methodName* jako metodu test. `TEST_METHOD`musí být deklarován v oboru metody třídy.  
  
###  <a name="Initialize_and_cleanup"></a>Inicializace a čištění  
  
####  <a name="test_methods"></a>Test metody  
  
```cpp  
TEST_METHOD_INITIALIZE(methodName)   
{  
    // method initialization code  
}  
  
```  
  
 Definuje *methodName* jako metodu, která se spustí před každou metodu test běží. `TEST_METHOD_INITIALIZE`může být definovaný jenom jednou v třídě test a musí být definovaný ve třídě testu.  
  
```cpp  
TEST_METHOD_CLEANUP(methodName)   
{  
    // test method cleanup  code  
}  
  
```  
  
 Definuje *methodName* jako metodu, která spustí po spuštění každé metody test. `TEST_METHOD_CLEANUP`může být definovaný jenom jednou v třídě test a musí být definován v oboru třídy testu.  
  
####  <a name="test_classes"></a>Test třídy  
  
```cpp  
TEST_CLASS_INITIALIZE(methodName)   
{  
    // test class initialization  code  
}  
```
  
 Definuje *methodName* jako metodu, která spustí po vytvoření každé třídě testu. `TEST_CLASS_INITIALIZE`může být definovaný jenom jednou v třídě test a musí být definován v oboru třídy testu.  
  
```cpp  
TEST_CLASS_CLEANUP(methodName)   
{  
    // test class cleanup  code  
}  
```
  
 Definuje *methodName* jako metodu, která spustí po vytvoření každé třídě testu. `TEST_CLASS_CLEANUP`může být definovaný jenom jednou v třídě test a musí být definován v oboru třídy testu.  
  
####  <a name="test_modules"></a>Test moduly  
  
```cpp  
TEST_MODULE_INITIALIZE(methodName)  
{  
    // module initialization code  
}  
```  
  
 Definuje metodu *methodName* používající při načtení modulu. `TEST_MODULE_INITIALIZE`může být definovaný jenom jednou v modulu testování a musí být deklarován v oboru názvů.  
  
```cpp  
TEST_MODULE_CLEANUP(methodName)  
```  
  
 Definuje metodu *methodName* , spustí, když modul je odpojen. `TEST_MODULE_CLEANUP`může být definovaný jenom jednou v modulu testování a musí být deklarován v oboru názvů.  
  
###  <a name="create_test_attributes"></a>Vytvořte atributy testu  
  
####  <a name="test_method_attributes"></a>Atributy metody testu  
  
```cpp  
BEGIN_TEST_METHOD_ATTRIBUTE(testMethodName)   
    TEST_METHOD_ATTRIBUTE(attributeName, attributeValue)  
    ...  
END_TEST_METHOD_ATTRIBUTE()  
```  
  
 Přidá atributy definované s jedním nebo více `TEST_METHOD_ATTRIBUTE` makra metodu test *testClassName*.  
  
 A `TEST_METHOD_ATTRIBUTE` makro definuje atribut s názvem *attributeName* a hodnotu *vlastnost attributeValue*.  
  
####  <a name="test_class_attributes"></a>Atributy třídy testu  
  
```cpp  
BEGIN_TEST_CLASS_ATTRIBUTE(testClassName)   
    TEST_CLASS_ATTRIBUTE(attributeName, attributeValue)  
    ...  
END_TEST_CLASS_ATTRIBUTE()  
```  
  
 Přidá atributy definované s jedním nebo více `TEST_CLASS_ATTRIBUTE` makra k třídě test *testClassName*.  
  
 A `TEST_CLASS_ATTRIBUTE` makro definuje atribut s názvem *attributeName* a hodnotu *vlastnost attributeValue*.  
  
####  <a name="test_module_attributes"></a>Atributy modulu testu  
  
```cpp  
BEGIN_TEST_MODULE_ATTRIBUTE(testModuleName)   
    TEST_MODULE_ATTRIBUTE(attributeName, attributeValue)  
    ...  
END_TEST_MODULE_ATTRIBUTE()  
```  
  
 Přidá atributy definované s jedním nebo více `TEST_MODULE_ATTRIBUTE` maker, pro modul testu *testModuleName*.  
  
 A `TEST_MODULE_ATTRIBUTE` makro definuje atribut s názvem *attributeName* a hodnotu *vlastnost attributeValue*.  
  
####  <a name="pre_defined_attributes"></a>Předem definované atributy  
 Tyto makra předem definovaný atribut se můžou nahradit pro makra `TEST_METHOD_ATTRIBUTE`, `TEST_CLASS_ATTRIBUTE`, nebo `TEST_MODULE_ATTRIBUTE` popsané výše.  
  
```cpp  
TEST_OWNER(ownerAlias)  
```  
  
 Definuje atribut s názvem `Owner` a hodnotu atributu *ownerAlias*.  
  
```cpp  
TEST_DESCRIPTION(description)  
```  
  
 Definuje atribut s názvem `Description` a hodnotu atributu *popis*.  
  
```cpp  
TEST_PRIORITY(priority)  
```  
  
 Definuje atribut s názvem `Priority` a hodnotu atributu *s prioritou*.  
  
```cpp  
TEST_WORKITEM(workitem)  
```  
  
 Definuje atribut s názvem `WorkItem` a hodnotu atributu *pracovní položka*.  
  
```cpp  
TEST_IGNORE()  
```  
  
 Definuje atribut s názvem `Ignore` a hodnotu atributu `true`.  
  
##  <a name="cppUnitTestAssert_h"></a>CppUnitTestAssert.h  
  
###  <a name="general_asserts"></a>Vyhodnotí obecné  
  
####  <a name="general_are_equal"></a>Jsou stejné  
 Ověřte, že jsou oba objekty stejné  
  
```cpp  
template<typename T>   
static void Assert::AreEqual(  
    const T& expected,   
    const T& actual,   
    const wchar_t* message = NULL,   
    const __LineInfo* pLineInfo = NULL)  
```  
  
 Ověřte, zda jsou si rovny dvě hodnoty Double  
  
```cpp  
static void Assert::AreEqual(  
    double expected,   
    double actual,   
    double tolerance,   
    const wchar_t* message = NULL,   
    const __LineInfo* pLineInfo = NULL)  
```  
  
 Ověřte, zda jsou dva obtékaných objektů stejné  
  
```cpp  
static void Assert::AreEqual(  
    float expected,   
    float actual,   
    float tolerance,   
    const wchar_t* message = NULL,   
    const __LineInfo* pLineInfo = NULL)  
```  
  
 Ověřte, zda jsou dva typu char * řetězce stejné  
  
```cpp  
static void Assert::AreEqual(  
    const char* expected,   
    const char* actual,   
    bool ignoreCase = false,   
    const wchar_t* message = NULL,   
    const __LineInfo* pLineInfo = NULL)  
```  
  
 Ověřte, zda jsou si rovny dva w_char * řetězce  
  
```cpp  
static void Assert::AreEqual(  
    const wchar_t* expected,   
    const wchar_t* actual,   
    bool ignoreCase = false,   
    const wchar_t* message = NULL,   
    const __LineInfo* pLineInfo = NULL)  
```  
  
####  <a name="general_are_not_equal"></a>Nejsou stejné  
 Ověřte, že dvě hodnoty Double nejsou stejné  
  
```cpp  
static void Assert::AreNotEqual(  
    double notExpected,   
    double actual,   
    double tolerance,   
    const wchar_t* message = NULL,   
    const __LineInfo* pLineInfo = NULL)  
```  
  
 Ověřte, že dvě obtékané objekty nejsou stejné  
  
```cpp  
static void Assert::AreNotEqual(  
    float notExpected,   
    float actual,   
    float tolerance,   
    const wchar_t* message = NULL,   
    const __LineInfo* pLineInfo = NULL)  
```  
  
 Ověřte, že dva typu char * řetězce nejsou stejné  
  
```cpp  
static void Assert::AreNotEqual(  
    const char* notExpected,   
    const char* actual,   
    bool ignoreCase = false,   
    const wchar_t* message = NULL,   
    const __LineInfo* pLineInfo = NULL)  
```  
  
 Ověřte, že dva w_char * řetězce nejsou stejné  
  
```cpp  
static void Assert::AreNotEqual(  
    const wchar_t* notExpected,   
    const wchar_t* actual,   
    bool ignoreCase = false,   
    const wchar_t* message = NULL,   
    const __LineInfo* pLineInfo = NULL)  
```  
  
 Ověřte, že dva odkazy nejsou stejné podle operátor ==.  
  
```cpp  
template<typename T>   
static void Assert::AreNotEqual(  
    const T& notExpected,   
    const T& actual,   
    const wchar_t* message = NULL,   
    const __LineInfo* pLineInfo = NULL)  
```  
  
####  <a name="general_are_same"></a>Jsou stejné  
 Ověřte, že dva odkazy odkazují na stejnou instanci objektu (identity).  
  
```cpp  
template<typename T>   
static void Assert::AreSame(  
    const T& expected,   
    const T& actual,   
    const wchar_t* message = NULL,   
    const __LineInfo* pLineInfo = NULL)  
```  
  
####  <a name="general_are_not_same"></a>Nejsou stejné  
 Ověřte, že dvě neodkazovaly na stejnou instanci objektu (identity).  
  
```cpp  
template<typename T>   
static void Assert::AreNotSame (  
    const T& notExpected,   
    const T& actual,   
    const wchar_t* message = NULL,   
    const __LineInfo* pLineInfo = NULL)  
```  
  
####  <a name="general_is_null"></a>Má hodnotu Null.  
 Ověřte, zda je ukazatel hodnotu NULL.  
  
```cpp  
template<typename T>   
static void Assert::IsNull(  
    const T* actual,  
    const wchar_t* message = NULL,   
    const __LineInfo* pLineInfo = NULL)  
```  
  
####  <a name="general_is_not_null"></a>Nemá hodnotu Null  
 Ověřte, že ukazatel není NULL.  
  
```cpp  
template<typename T>   
static void Assert::IsNotNull(  
    const T* actual,   
    const wchar_t* message = NULL,   
    const __LineInfo* pLineInfo = NULL)  
```  
  
####  <a name="general_is_True"></a>Hodnotu True  
 Ověřte, zda je podmínka true  
  
```cpp  
static void Assert::IsTrue(  
    bool condition,   
    const wchar_t* message = NULL,   
    const __LineInfo* pLineInfo = NULL)  
```  
  
####  <a name="general_is_false"></a>Je hodnota False  
 Ověřte, zda je podmínka false  
  
```cpp  
static void Assert::IsFalse(  
    bool condition,   
    const wchar_t* message = NULL,   
    const __LineInfo* pLineInfo = NULL)  
```  
  
####  <a name="general_Fail"></a>Selhání  
 Vynutit výsledek testovacího případu, který má být se nezdařilo  
  
```cpp  
static void Assert::Fail(  
    const wchar_t* message = NULL,   
    const __LineInfo* pLineInfo = NULL)  
```  
  
###  <a name="winrt_asserts"></a>Vyhodnotí prostředí Windows Runtime  
  
####  <a name="winrt_are_equal"></a>Jsou stejné  
 Ověřuje, zda jsou si rovny dvě prostředí Windows Runtime ukazatele.  
  
```cpp  
template<typename T>   
static void Assert::AreEqual(  
    T^ expected,   
    T^ actual,   
    Platform::String^ message = nullptr,   
    const __LineInfo* pLineInfo= nullptr)  
```  
  
 Ověřuje, že dva Platform::String ^ řetězce jsou stejné.  
  
```cpp  
template<typename T>   
static void Assert::AreEqual(  
    T^ expected,   
    T^ actual,   
    Platform::String^ message= nullptr,   
    const __LineInfo* pLineInfo= nullptr)  
```  
  
####  <a name="winrt_are_same"></a>Jsou stejné  
 Ověřuje, že dvě prostředí Windows Runtime odkazy odkazují na stejný objekt.  
  
```cpp  
template<typename T>   
static void Assert::AreSame(  
    T% expected,   
    T% actual,   
    Platform::String^ message= nullptr,   
    const __LineInfo* pLineInfo= nullptr)  
```  
  
####  <a name="winrt_are_not_equal"></a>Nejsou stejné  
 Ověřuje, že dva ukazatele prostředí Windows Runtime nejsou stejné.  
  
```cpp  
template<typename T>   
static void Assert::AreNotEqual(  
    T^ notExpected,   
    T^ actual,   
    Platform::String^ message = nullptr,   
    const __LineInfo* pLineInfo= nullptr)  
```  
  
 Ověřuje, že dva Platform::String ^ řetězce se neshodují.  
  
```cpp  
static void Assert::AreNotEqual(  
    Platform::String^ notExpected,   
    Platform::String^ actual,   
    bool ignoreCase = false,   
    Platform::String^ message= nullptr,   
    const __LineInfo* pLineInfo= nullptr)  
```  
  
####  <a name="winrt_are_not_same"></a>Nejsou stejné  
 Ověřuje, že dva odkazy na prostředí Windows Runtime neodkazují na stejný objekt.  
  
```cpp  
template<typename T>   
static void Assert::AreNotSame(  
    T% notExpected,   
    T% actual,   
    Platform::String^ message= nullptr,   
    const __LineInfo* pLineInfo= nullptr)  
```  
  
####  <a name="winrt_is_null"></a>Má hodnotu Null.  
 Ověří, že prostředí Windows Runtime ukazatel nullptr.  
  
```cpp  
template<typename T>   
static void Assert::IsNull(  
    T^ actual,  
    Platform::String^ message = nullptr,   
    const __LineInfo* pLineInfo= nullptr)  
```  
  
####  <a name="winrt_is_not_null"></a>Nemá hodnotu Null  
 Ověřuje, že prostředí Windows Runtime ukazatel není nullptr.  
  
```cpp  
template<typename T>   
static void Assert::IsNotNull(  
    T^ actual,   
    Platform::String^ message= nullptr,   
    const __LineInfo* pLineInfo= nullptr)  
```  
  
###  <a name="exception_asserts"></a>Vyhodnotí výjimky  
  
####  <a name="expect_exception"></a>Očekávané výjimky  
 Ověřte, že funkce vyvolá výjimku:  
  
```cpp  
template<typename _EXPECTEDEXCEPTION, typename _FUNCTOR>   
static void Assert::ExpectException(  
    _FUNCTOR functor,   
    const wchar_t* message= NULL,   
    const __LineInfo* pLineInfo= NULL)  
```  
  
 Ověřte, že funkce vyvolá výjimku:  
  
```cpp  
template<typename _EXPECTEDEXCEPTION, typename _RETURNTYPE>   
    static void Assert::ExpectException(  
    _RETURNTYPE (*func)(),   
    const wchar_t* message= NULL,   
    const __LineInfo* pLineInfo = NULL)  
```  
  
##  <a name="cppunittestlogger_h"></a>CppUnitTestLogger.h  
  
###  <a name="logger"></a>Protokoly  
 Třída protokolovacího nástroje obsahuje statických metod k zápisu **výstup – okno**. 
  
###  <a name="write_message"></a>Zapsat zprávu  
Zápis řetězec tak, aby **výstup – okno**  

```cpp  
static void Logger::WriteMessage(const wchar_t* message)  
```  
  
```cpp  
static void Logger::WriteMessage(const char* message)  
```  
  
## <a name="example"></a>Příklad  
 Tento kód je příkladem VSCppUnit využití. Obsahuje příklady atribut metadat, zařízení, testování částí s kontrolní výrazy a vlastní protokolování. 
  
```cpp  
// USAGE EXAMPLE  
  
#include <CppUnitTest.h>  
  
using namespace Microsoft::VisualStudio::CppUnitTestFramework;  
  
BEGIN_TEST_MODULE_ATTRIBUTE()  
    TEST_MODULE_ATTRIBUTE(L"Date", L"2010/6/12")  
END_TEST_MODULE_ATTRIBUTE()  
  
TEST_MODULE_INITIALIZE(ModuleInitialize)  
{  
    Logger::WriteMessage("In Module Initialize");  
}  
  
TEST_MODULE_CLEANUP(ModuleCleanup)  
{  
    Logger::WriteMessage("In Module Cleanup");  
}  
  
TEST_CLASS(Class1)  
{  
  
public:  
  
    Class1()  
    {  
        Logger::WriteMessage("In Class1");  
    }  
  
    ~Class1()  
    {  
        Logger::WriteMessage("In ~Class1");  
    }  
  
    TEST_CLASS_INITIALIZE(ClassInitialize)  
    {  
        Logger::WriteMessage("In Class Initialize");  
    }  
  
    TEST_CLASS_CLEANUP(ClassCleanup)  
    {  
        Logger::WriteMessage("In Class Cleanup");  
    }  
  
    BEGIN_TEST_METHOD_ATTRIBUTE(Method1)  
        TEST_OWNER(L"OwnerName")  
        TEST_PRIORITY(1)  
    END_TEST_METHOD_ATTRIBUTE()  
  
    TEST_METHOD(Method1)  
    {     
        Logger::WriteMessage("In Method1");  
        Assert::AreEqual(0, 0);  
    }  
  
    TEST_METHOD(Method2)  
    {  
        Assert::Fail(L"Fail");  
    }  
};  
```  
  
## <a name="see-also"></a>Viz také  
 [Testování částí kódu](../test/unit-test-your-code.md)   
 [Zápis testů částí pro C/C++](writing-unit-tests-for-c-cpp.md)   

