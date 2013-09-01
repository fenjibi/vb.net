Imports MySql.Data.MySqlClient
Imports System.IO
Public Class Form1
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click
        Dim connstring As String = "Database=pmk;data source=localhost;user id=root;password="
        Dim Sql As String = "select * from mastermahasiswa where Nim='" & TextBox1.Text & "'"
        Dim conn As New MySqlConnection(connstring)
        Dim cmd As New MySqlCommand(Sql, conn)
        Dim dr As MySqlDataReader = Nothing
        Try
        conn.Open()
        dr = cmd.ExecuteReader()
        dr.Read()
        Dim imagebytes As Byte() = CType(dr("Foto"), Byte())
        Using ms As New IO.MemoryStream(imagebytes)
            PictureBox1.Image = Image.FromStream(ms)
            PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage
        End Using
        MsgBox("nih fotonya muncul")
        Catch ex As Exception
        
        End Try
        conn.Close()
    End Sub
End Class
