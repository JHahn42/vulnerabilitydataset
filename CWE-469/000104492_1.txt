#include "std_testcase.h"

#include <wchar.h>

#define SOURCE_STRING L"abc/opqrstu"



void func1()
{
    switch(6)
    {
    case 6:
    {
        wchar_t string1[] = SOURCE_STRING;
        wchar_t string2[] = SOURCE_STRING;
        wchar_t * slashInString1;
        size_t indexOfSlashInString1;
        slashInString1 = wcschr(string1, L'/');
        if (slashInString1 == NULL)
        {
            exit(1);
        }
        indexOfSlashInString1 = (size_t)(slashInString1 - string2);
        printUnsignedLine(indexOfSlashInString1);
    }
    break;
    default:
        printLine("Benign, fixed string");
        break;
    }
}



int main(int argc, char * argv[])
{
    srand( (unsigned)time(NULL) );

    printLine("Calling ...");
    func1();
    printLine("Finished");
    return 0;
}

