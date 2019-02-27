#include "std_testcase.h"

#include <wchar.h>

#define SOURCE_STRING "abc/opqrstu"



static void func3()
{
    switch(5)
    {
    case 6:
        printLine("Benign, fixed string");
        break;
    default:
    {
        char string1[] = SOURCE_STRING;
        char * slashInString1;
        size_t indexOfSlashInString1;
        slashInString1 = strchr(string1, '/');
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
        char string1[] = SOURCE_STRING;
        char * slashInString1;
        size_t indexOfSlashInString1;
        slashInString1 = strchr(string1, '/');
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

