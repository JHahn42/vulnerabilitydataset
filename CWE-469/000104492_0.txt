#include "std_testcase.h"

#include <wchar.h>

#define SOURCE_STRING L"abc/opqrstu"



static void func3()
{
    switch(5)
    {
    case 6:
        printLine("Benign, fixed string");
        break;
    default:
    {
        wchar_t string1[] = SOURCE_STRING;
        wchar_t * slashInString1;
        size_t indexOfSlashInString1;
        slashInString1 = wcschr(string1, L'/');
        if (slashInString1 == NULL)
        {
            exit(1);
        }
        indexOfSlashInString1 = (size_t)(slashInString1 - string1);
        printUnsignedLine(indexOfSlashInString1);
    }
    break;
    }
}

static void func5()
{
    switch(6)
    {
    case 6:
    {
        wchar_t string1[] = SOURCE_STRING;
        wchar_t * slashInString1;
        size_t indexOfSlashInString1;
        slashInString1 = wcschr(string1, L'/');
        if (slashInString1 == NULL)
        {
            exit(1);
        }
        indexOfSlashInString1 = (size_t)(slashInString1 - string1);
        printUnsignedLine(indexOfSlashInString1);
    }
    break;
    default:
        printLine("Benign, fixed string");
        break;
    }
}

void func7()
{
    func3();
    func5();
}



int main(int argc, char * argv[])
{
    srand( (unsigned)time(NULL) );

    printLine("Calling ...");
    func7();
    printLine("Finished");
    return 0;
}

