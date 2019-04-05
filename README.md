# Lab-5-Text-Edior
Lab 6 NETD
Public Class frmLab5
    Private Sub ToolStripButton1_Click(sender As Object, e As EventArgs)

    End Sub

    Private Sub OpenToolStripMenuItem_Click(sender As Object, e As EventArgs) Handles tmiOpen.Click
        Dim ofd As New OpenFileDialog
        Dim location As String
        ofd.ShowDialog()
        location = ofd.FileName
        Dim sr As New System.IO.StreamReader(location)
        rtbInput.Text = sr.ReadToEnd()
        sr.Close()
    End Sub

    Private Sub SaveAsToolStripMenuItem_Click(sender As Object, e As EventArgs) Handles tmiSaveAs.Click
        Dim sfd As New SaveFileDialog
        Dim sv As String
        sfd.ShowDialog()
        sv = sfd.FileName
        Dim sw As New System.IO.StreamWriter(sv)
        sw.Write(rtbInput.Text)
        sw.Close()
    End Sub

    Private Sub ToolStripDropDownButton2_Click(sender As Object, e As EventArgs) Handles tsbEdit.Click

    End Sub

    Private Sub AboutToolStripMenuItem_Click(sender As Object, e As EventArgs) Handles tmiAbout.Click
        MessageBox.Show("Lab 5 NetD Phillip Rodgers")
    End Sub

    Private Sub ExitToolStripMenuItem_Click(sender As Object, e As EventArgs) Handles tmiExit.Click
        Me.Close()
    End Sub

    Private Sub CloseToolStripMenuItem_Click(sender As Object, e As EventArgs) Handles tmiClose.Click
        Me.rtbInput.Clear()
    End Sub

    Private Sub NewToolStripMenuItem_Click(sender As Object, e As EventArgs) Handles tmiNew.Click
        Me.rtbInput.Clear()
    End Sub

    Private Sub CopyToolStripMenuItem_Click(sender As Object, e As EventArgs) Handles tmiCopy.Click
        Dim textSelected As String
        textSelected = rtbInput.SelectedText
        My.Computer.Clipboard.SetText(textSelected)
    End Sub

    Private Sub PasteToolStripMenuItem_Click(sender As Object, e As EventArgs) Handles tmiPaste.Click
        My.Computer.Clipboard.GetText()
    End Sub
    Private Sub CutToolStripMenuItem_Click(sender As Object, e As EventArgs) Handles tmiCut.Click
        Dim textSelected As String
        textSelected = rtbInput.SelectedText
        My.Computer.Clipboard.SetText(textSelected)
        rtbInput.SelectedText = ""
    End Sub

    Private Sub tsbFile_Click(sender As Object, e As EventArgs) Handles tsbFile.Click

    End Sub
End Class
