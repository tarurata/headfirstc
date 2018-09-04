#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main(int argc, char *argv[])
{
    char line[80];

//引数が6以外だったら標準エラー出力にエラーを表示
    if ( argc != 6 ) {
        fprintf( stderr, "You need to give 5 arguments\n");
        return 1;
    }
//ファイル構造体のPOINTERを作成。spooky.csvは読み出し。ほかは書き込み。
    FILE *in = fopen("spooky.csv", "r");
    FILE *file1 = fopen(argv[2], "w");
    FILE *file2 = fopen(argv[4], "w");
    FILE *file3 = fopen(argv[5], "w");

//fscanf(入力先を指定して)
//spooky.csvから読み出したデータをlineに入力。fscanfは処理に成功したらデータの個数（この場合1）を返す
    while (fscanf(in, "%79[^\n]\n", line) == 1){

//aline(入力されたデータを)のなかをstrstrで引数の1つめに合致するか確認。合致しなければ3つめの引数と合致するか確認。
        if (strstr(line, argv[1]))
            fprintf(file1, "%s\n", line);

        else if (strstr(line, argv[3]))
            fprintf(file2, "%s\n", line);
        else 
            fprintf(file3, "%s\n", line);
    }
    fclose(file1);
    fclose(file2);
    fclose(file3);
    return 0;
}

