# POS-Billing-Management-system-using-VB.Net

Public Class Form1
    Const Tomatoes = 15
    Const Rice = 90
    Const Mangoes = 75
    Const Carrots = 20
    Const BellPeppers = 15
    Const Ragi = 65
    Const Spinach = 10

    Dim Items(9)
    Private Sub Panel2_Paint(sender As Object, e As PaintEventArgs) Handles Panel2.Paint, Panel6.Paint, Panel5.Paint, Panel4.Paint, Panel3.Paint

    End Sub

    Private Sub btnExit_Click(sender As Object, e As EventArgs) Handles btnExit.Click
        Dim iQuit As DialogResult

        iQuit = MessageBox.Show("Confirm if you want to quit", "Billing Management System",
        MessageBoxButtons.YesNo, MessageBoxIcon.Question)

        If iQuit = DialogResult.Yes Then
            Application.Exit()
        End If
    End Sub

    Private Sub NumTomatoes_ValueChanged(sender As Object, e As EventArgs) Handles NumTomatoes.ValueChanged
        lblTomatoes.Text = FormatCurrency(NumTomatoes.Value * Tomatoes)
    End Sub

    Private Sub NumRice_ValueChanged(sender As Object, e As EventArgs) Handles NumRice.ValueChanged
        lblRice.Text = FormatCurrency(NumRice.Value * Rice)
    End Sub

    Private Sub NumMangoes_ValueChanged(sender As Object, e As EventArgs) Handles NumMangoes.ValueChanged
        lblMangoes.Text = FormatCurrency(NumMangoes.Value * Mangoes)
    End Sub

    Private Sub NumCarrots_ValueChanged(sender As Object, e As EventArgs) Handles NumCarrots.ValueChanged
        lblCarrots.Text = FormatCurrency(NumCarrots.Value * Carrots)
    End Sub

    Private Sub NumBellPeppers_ValueChanged(sender As Object, e As EventArgs) Handles NumBellPeppers.ValueChanged
        lblBellPeppers.Text = FormatCurrency(NumBellPeppers.Value * BellPeppers)
    End Sub

    Private Sub NumRagi_ValueChanged(sender As Object, e As EventArgs) Handles NumRagi.ValueChanged
        lblRagi.Text = FormatCurrency(NumRagi.Value * Ragi)
    End Sub

    Private Sub NumSpinach_ValueChanged(sender As Object, e As EventArgs) Handles NumSpinach.ValueChanged
        lblSpinach.Text = FormatCurrency(NumSpinach.Value * Spinach)
    End Sub

    Private Sub btnReset_Click(sender As Object, e As EventArgs) Handles btnReset.Click
        NumTomatoes.Value = 0
        NumRice.Value = 0
        NumMangoes.Value = 0
        NumCarrots.Value = 0
        NumBellPeppers.Value = 0
        NumRagi.Value = 0
        NumSpinach.Value = 0

        lblTomatoes.Text = "Rs 0.0"
        lblRice.Text = "Rs 0.0"
        lblMangoes.Text = "Rs 0.0"
        lblCarrots.Text = "Rs 0.0"
        lblBellPeppers.Text = "Rs 0.0"
        lblRagi.Text = "Rs 0.0"
        lblSpinach.Text = "Rs 0.0"
        lblTotal.Text = "Rs 0.0"
        lblNumItems.Text = 0
        rtReceipt.Clear()
    End Sub

    Private Sub btnTotal_Click(sender As Object, e As EventArgs) Handles btnTotal.Click
        Items(0) = NumTomatoes.Value * Tomatoes
        Items(1) = NumRice.Value * Rice
        Items(2) = NumMangoes.Value * Mangoes
        Items(3) = NumCarrots.Value * Carrots
        Items(4) = NumBellPeppers.Value * BellPeppers
        Items(5) = NumRagi.Value * Ragi
        Items(6) = NumSpinach.Value * Spinach

        Items(7) = Items(0) + Items(1) + Items(2) + Items(3) + Items(4) + Items(5) + Items(6)
        lblTotal.Text = FormatCurrency(Items(7))

        Dim q(9)
        q(0) = NumTomatoes.Value
        q(1) = NumRice.Value
        q(2) = NumMangoes.Value
        q(3) = NumCarrots.Value
        q(4) = NumBellPeppers.Value
        q(5) = NumRagi.Value
        q(6) = NumSpinach.Value
        q(7) = q(0) + q(1) + q(2) + q(3) + q(4) + q(5) + q(6)

        lblNumItems.Text = q(7)


    End Sub

    Private Sub btnReceipt_Click(sender As Object, e As EventArgs) Handles btnReceipt.Click
        rtReceipt.Clear()
        rtReceipt.AppendText(Label17.Text & vbTab & Label18.Text & vbTab & Label19.Text & vbNewLine & vbNewLine)

        rtReceipt.AppendText(lblItemTomatoes.Text & vbTab & vbTab & NumTomatoes.Value & vbTab & vbTab & vbTab & lblTomatoes.Text & vbNewLine & vbNewLine)
        rtReceipt.AppendText(lblItemRice.Text & vbTab & vbTab & vbTab & NumRice.Value & vbTab & vbTab & vbTab & lblRice.Text & vbNewLine & vbNewLine)
        rtReceipt.AppendText(lblItemMangoes.Text & vbTab & vbTab & NumMangoes.Value & vbTab & vbTab & vbTab & lblMangoes.Text & vbNewLine & vbNewLine)
        rtReceipt.AppendText(lblItemCarrots.Text & vbTab & vbTab & NumCarrots.Value & vbTab & vbTab & vbTab & lblCarrots.Text & vbNewLine & vbNewLine)
        rtReceipt.AppendText(lblItemBellPeppers.Text & vbTab & NumBellPeppers.Value & vbTab & vbTab & vbTab & lblBellPeppers.Text & vbNewLine & vbNewLine)
        rtReceipt.AppendText(lblItemRagi.Text & vbTab & vbTab & vbTab & NumRagi.Value & vbTab & vbTab & vbTab & lblRagi.Text & vbNewLine & vbNewLine)
        rtReceipt.AppendText(lblItemSpinach.Text & vbTab & vbTab & NumSpinach.Value & vbTab & vbTab & vbTab & lblSpinach.Text & vbNewLine & vbNewLine)


        rtReceipt.AppendText(lblItemTotal.Text & vbTab & vbTab & lblNumItems.Text & vbTab & vbTab & vbTab & lblTotal.Text & vbNewLine & vbNewLine)
    End Sub
End Class
