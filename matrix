#include <stdio.h>
#include <stdlib.h>

struct node {
    int row, column, data;
    struct node *next;
    struct node *pre;
};
typedef struct node * NODE;

NODE insert_end(NODE start, int r, int c, int item) {
    NODE temp, curr;
    temp = (NODE)malloc(sizeof(struct node));
    temp->row = r;
    temp->column = c;
    temp->data = item;
    temp->next = NULL;
    temp->pre = NULL;

    if (start == NULL)
        return temp;

    curr = start;
    while (curr->next != NULL)
        curr = curr->next;

    curr->next = temp;
    temp->pre = curr;

    return start;
}

void display(NODE start) {
    NODE temp;
    if (start == NULL)
        printf("\nList is empty");
    else {
        printf("\nRow\tColumn\tData\n");
        temp = start;
        while (temp != NULL) {
            printf("%d\t%d\t%d\n", temp->row, temp->column, temp->data);
            temp = temp->next;
        }
    }
}

void display_matrix(NODE start, int m, int n) {
    NODE temp = start;
    int i, j;

    for (i = 1; i <= m; i++) {
        for (j = 1; j <= n; j++) {
            if (temp != NULL && temp->row == i && temp->column == j) {
                printf("%d\t", temp->data);
                temp = temp->next;
            } else {
                printf("0\t");
            }
        }
        printf("\n");
    }
}

int main() {
    int i, j, m, n, item;
    NODE start = NULL;

    printf("\nEnter the order of the matrix (m n): ");
    scanf("%d %d", &m, &n);

    printf("\nEnter elements:\n");
    for (i = 1; i <= m; i++) {
        for (j = 1; j <= n; j++) {
            scanf("%d", &item);
            if (item != 0)
                start = insert_end(start, i, j, item);
        }
    }

    display(start);

    printf("\nActual matrix is:\n");
    display_matrix(start, m, n);

    return 0;
}
