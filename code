//896 Kiểm tra cây nhị phân T có phải là "cây nhị phân cân bằng hoàn toàn" hay không?
//cây nhị phân cân bằng hoàn toàn là cây nhị phân tìm kiếm mà tại mỗi nút của nó 
//số nút của cây con trái và cây con phải chêch lệch ko quá 1
//0 là cây nhị phân tìm kiếm
//1 ko phải là cây nhị phân tìm kiếm
void TimMax(Tree c, int &Max)
{
    if (c==NULL)
        return ;
    if (c->pLeft != NULL)
        Max = (Max > c->pLeft->iX)? Max : c->pLeft->iX;
    if (c->pRight != NULL)
        Max = (Max > c->pRight->iX)? Max : c->pRight->iX;
    Max = (Max > c->iX) ? Max : c->iX;
    TimMax(c->pLeft,Max);
    TimMax(c->pRight,Max);
}
int DemNode(Tree c)
{
    if (c==NULL)
        return 0;
    int DemR = DemNode(c->pRight);
    int DemL = DemNode(c->pLeft);
    return DemR + DemL + 1;
}

int KiemTra(Tree c)
{
    if (c==NULL)
        return 0;
    int Left = KiemTra(c->pLeft);
    //kiểm tra điều kiện của cây nhị phân tìm kiếm
    int MaxL, MaxR;
    if (c->pLeft != NULL && c->pRight != NULL)
    {
        TimMax(c->pLeft, MaxL);
        TimMax(c->pRight, MaxR);
        if (!(MaxL < c->iX && c->iX < MaxR))
            return 1;
    }
    else if (c->pLeft == NULL && c->pRight != NULL)
    {
        TimMax(c->pRight, MaxR);
        if (!(c->iX < MaxR))
            return 1;
    }
    else if (c->pLeft != NULL && c->pRight == NULL)
    {
        TimMax(c->pLeft, MaxL);
        if (!(MaxL < c->iX))
            return 1;
    }
    //kiểm tra điều kiện của cây nhị phân tìm kiếm cân bằng hoàn toàn
    int NodeR = DemNode(c->pRight);
    int NodeL = DemNode(c->pLeft);
    printf ("ntnode: %d lech Right: %d, Left: %d", c->iX,NodeR,NodeL);
    if (abs(NodeR - NodeL) > 1)    //chêch lệch lớn hơn 1
        return 1;
    int Right = KiemTra(c->pRight);
    return Left + Right;
}
void XuatKqKiemTra(Tree c)
{
    int Kt = KiemTra(c);
    if (Kt == 0)
        printf("nla cay nhi phan tim kiem can bang hoan toan");
    else
        printf("nko phai cay nhi phan tim kiem can bang hoan toan");
}
