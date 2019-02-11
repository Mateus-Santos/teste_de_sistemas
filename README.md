import unittest



class MyModuleTest(unittest.TestCase):
  def setUp(self):

     self.contas=[]
     #nome,CPF,id,limite de crédito,saldo,senha

     self.contas.append('Lucas ',56789789064,1,1500.00,5000.00,12345678)

     self.contas.append('Mateus ',20345766789,2,5000.00,9843818)

     self.contas.append('Ronaldo ',20567890711,3,4500.00,42353626)

     self.contas.append('Leonardo ',37812456751,4,3000.00,23462346)


  def test_deletar_conta(self):

     #remover pelo id,cpf e senha

     self.contas.remove_conta((3,20567890711,42353626),'Conta removida com sucesso!')

     self.assertFalse(contas.verifica_existencia(3),'Algo está errado!')

     self.assertFalse(contas.verifica_existencia(3,134,678),'Algo está errado!')


  def test_alterar_limite_cred(self):

     #alterar limite pelo id

     self.assertEqual(contas.alterar_limite(2,450000.00),'Limite alterado com sucesso!')

     self.assertEqual(contas.alterar_limite(2,0),'O limite não foi alterado!')

     self.assertEqual(contas.alterar_limite(2,-1),'Erro: não é possivel alterar o limite com números negativos!')

     self.assertEqual(contas.alterar_limite(-1, -1),'ID não encontrado!')


  def test_receber_deposito(self):

     self.assertEqual(contas.receber_deposito(3,55555.00),'Deposito realizado com sucesso!')

     self.assertEqual(contas.receber_deposito(-1,500),'ID não encontrado!')

     self.assertEqual(contas.receber_deposito(1, -500), 'Impossivel realizar deposito com número negativo!')


  def test_transferencia(self):

     self.assertEqual(contas.realizar_transferencia(3,2,50.00),'Transferencia realizada com sucesso!')

     self.assertEqual(conta.realizar_transferencia(3,2,-50.00),'Impossivel realizar deposito com número negativo!')

     self.assertEqual(conta.realizar_transferencia(3, 70,50.00),'ID não encontrado!')


  def test_saque(self):

     self.assertEqual((3,30.00),'Transferencia realizada com sucesso!')

     self.assertEqual((3),'Algo está errado!')

     self.assertEqual((3,-50), 'Saque impossivel!')

     self.assertEquals((3,1000))


if __name__=='__main__':
  unittest.main()

