#include "std_testcase.h"

#include <wchar.h>

#define SOURCE_STRING L"abc/opqrstu"



static void func2()
{
    goto var1;
var1:
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
}

void func3()
{
    func2();
}



int main(int argc, char * argv[])
{
    srand( (unsigned)time(NULL) );

    printLine("Calling ...");
    func3();
    printLine("Finished");
    return 0;
}

