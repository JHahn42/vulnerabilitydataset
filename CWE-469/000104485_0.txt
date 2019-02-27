#include "std_testcase.h"

#include <wchar.h>

#define SOURCE_STRING L"abc/opqrstu"

static int staticReturnsTrue()
{
    return 1;
}

static int staticReturnsFalse()
{
    return 0;
}



static void func4()
{
    if(staticReturnsFalse())
    {
        printLine("Benign, fixed string");
    }
    else
    {
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
}

static void func5()
{
    if(staticReturnsTrue())
    {
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
}

void func6()
{
    func4();
    func5();
}



int main(int argc, char * argv[])
{
    srand( (unsigned)time(NULL) );

    printLine("Calling ...");
    func6();
    printLine("Finished");
    return 0;
}

