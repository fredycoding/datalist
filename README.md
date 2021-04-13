# Button and DropDownList inside Datalist ASP.NET
 Sub Item_Command(sender As Object, e As DataListCommandEventArgs) Handles DataList3.ItemCommand
        If e.CommandName = "GrabarIglesia" Then
            Dim IdIglesia As String = CType(e.Item.FindControl("IdLabel"), Label).Text

            Dim respuesta As String = CType(e.Item.FindControl("DropDownList1"), DropDownList).SelectedItem.Text
            Response.Write(respuesta & IdIglesia)

        End If
    End Sub
    *************************************************************
    
    
    Code in aspx
    
    <asp:DataList ID="DataList3" runat="server" DataSourceID="SqlDataSource2" CellPadding="4" ForeColor="#333333" DataKeyField="Id">
            <AlternatingItemStyle BackColor="White" />
            <FooterStyle BackColor="#507CD1" Font-Bold="True" ForeColor="White" />
            <HeaderStyle BackColor="#507CD1" Font-Bold="True" ForeColor="White" />
            <ItemStyle BackColor="#EFF3FB" />
            <ItemTemplate>
                Id:
                <asp:Label ID="IdLabel" runat="server" Text='<%# Eval("Id") %>' />
                <br />
                Ciudad:
                <asp:Label ID="CiudadLabel" runat="server" Text='<%# Eval("Ciudad") %>' />
                <br />
                Direccion:
                <asp:Label ID="DireccionLabel" runat="server" Text='<%# Eval("Direccion") %>' />
                <br />
                <asp:DropDownList ID="DropDownList1" runat="server" OnSelectedIndexChanged="DropDownList1_SelectedIndexChanged">
                    <asp:ListItem>Seleccione</asp:ListItem>
                    <asp:ListItem>Si</asp:ListItem>
                    <asp:ListItem>No</asp:ListItem>
                </asp:DropDownList>
                &nbsp;<asp:Button ID="BotonSalvarIglesiaAbierta" runat="server" CommandName="GrabarIglesia" Text="Guardar" />
                <br />
            </ItemTemplate>
            <SelectedItemStyle BackColor="#D1DDF1" Font-Bold="True" ForeColor="#333333" />
        </asp:DataList>
    
    
    
    
