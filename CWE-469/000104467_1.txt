#include "std_testcase.h"

#include <wchar.h>

#define SOURCE_STRING "abc/opqrstu"

static int staticReturnsTrue()
{
    return 1;
}

static int staticReturnsFalse()
{
    return 0;
}



void func3()
{
    if(staticReturnsTrue())
    {
        {
            char string1[] = SOURCE_STRING;
            char string2[] = SOURCE_STRING;
            char * slashInString1;
            size_t indexOfSlashInString1;
            slashInString1 = strchr(string1, '/');
            if (slashInString1 == NULL)
            {
                exit(1);
            }
            indexOfSlashInString1 = (size_t)(slashInString1 - string2);
            printUnsignedLine(indexOfSlashInString1);
        }
    }
}



int main(int argc, char * argv[])
{
    srand( (unsigned)time(NULL) );

    printLine("Calling ...");
    func3();
    printLine("Finished");
    return 0;
}

