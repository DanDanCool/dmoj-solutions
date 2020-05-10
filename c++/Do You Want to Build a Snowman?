#include <iostream>
#include <string>
#include <vector>
#include <fstream>

std::vector<std::string> snowman = {
    R"(|)", //0
    R"(\  |  /)", //1
    R"(\ | /)", //2
    R"(\|/)", //3
    R"(XXXXXXX)", //4
    R"(X       X)", //5
    R"(X  O   O  X)", //6
    R"(X     V     X)", //7
    R"(W   X  X     X  X)", //8
    R"(\   X  XXXXX  X)", //9
    R"(\   X       X)", //10
    R"(\   XXXXXXX)", //11
    R"(\ X       X---)", //12
    R"(X    O    X  \)", //13
    R"(X           X  \)", //14
    R"(XXXXXXXXXXX    \)", //15
    R"(X         X     M)", //16
    R"(OOOO OOOO      M)", //17
    R"(OOOO OOOO)" //18
};

std::vector<int> space = {
    10,
    7,
    8,
    9,
    7,
    6,
    5,
    4,
    0,
    1,
    2,
    3,
    4,
    5,
    4,
    5,
    5,
    6,
    6
};

void func(int N, std::ofstream& file)
{
    file.open("snowman.txt");
    int inc = -5;
    if (N > 2)
    {
        for (int i = 0; i < N; i++)
        {
            inc += i + 1;
        }
    }
    else
    {
        inc = 0;
    }
    for (int i = 0; i < 16; i++)
    {
        for (int j = 0; j < inc + space[i]; j++)
            file << " ";
        file << snowman[i] << "\n";
    }

    if (N > 1)
    {
        int num = 0;
        for (int j = 0; j < inc + space[16]; j++)
            file << " ";
        file << snowman[16] << "\n";

        for (int i = 1; i < N; i++) //torso
        {
            num += i;
            if (i > 1) //top
            {
                for (int j = 0; j < inc + 6 - num; j++)
                    file << " ";
                file << "X";
                for (int j = 0; j < 7 + num * 2; j++)
                    file << " ";
                file << "X" << "\n";
            }
            for (int j = 0; j < i + 1; j++) //midsection of torso
            {
                for (int k = 0; k < inc + 5 - num - j; k++)
                    file << " ";
                file << "X";
                for (int k = 0; k < 4 + num + j; k++)
                    file << " ";
                file << "O";
                for (int k = 0; k < 4 + num + j; k++)
                    file << " ";
                file << "X" << "\n";
            }
            for (int k = 0; k < inc + 4 - num - i; k++)
                file << " ";
            file << "X";
            for (int j = 0; j < (5 + num + i) * 2 + 1; j++)
                file << " ";
            file << "X" << "\n";
            for (int k = 0; k < inc + 5 - num - i; k++)
                file << " ";
            for (int j = 0; j < (5 + num + i) * 2 + 1; j++)
                file << "X";
            file << "\n";
        }
        for (int i = 0; i < 2; i++)
        {
            for (int k = 0; k < inc + space[18]; k++)
                file << " ";
            file << snowman[18] << "\n";
        }
    }
    else
    {
        for (int i = 0; i < space[17]; i++)
            file << " ";
        file << snowman[17] << "\n";
        for (int i = 0; i < space[17]; i++)
            file << " ";
        file << snowman[18] << "\n";
    }
    file.close();
}

int main()
{
    std::ofstream file;
    func(20, file);
}
