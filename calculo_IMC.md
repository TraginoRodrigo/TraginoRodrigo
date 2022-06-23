        private void btnSair_Click(object sender, EventArgs e)
        {
            Close();
        }

        private void btnLimpar_Click(object sender, EventArgs e)
        {
            txtPeso.Text = "";
            txtAltura.Text = "";
            txtImc.Text = "";
        }

        private void btnVerificar_Click(object sender, EventArgs e)
        {
            //declaração de variáveis
            //variável recebera conteudo do textbox;
            double peso, altura, imc;

            peso = Convert.ToDouble(txtPeso.Text);
            altura = Convert.ToDouble(txtAltura.Text);

            imc = peso / (altura * altura);
            //text box recebe conteudo da variável imc = resultado de calculo
            //definição com utilização de duas casa decimais
            txtImc.Text = imc.ToString("0.00");
            /* Em seguida condições de acordo com os resultados dos calculos
             * serão exibidas mensagens
             * configuração das messagebox, (mensagens, botoes, ícones)
             * como são várias condições temos um encadeamento de ifs*/

            if (imc < 18.49)
                MessageBox.Show("SITUAÇÃO: Você está abaixo do peso", "Cálculo de IMC", MessageBoxButtons.OK, MessageBoxIcon.Exclamation);
            else if (imc < 24.99)
                MessageBox.Show("SITUAÇÃO: Você está com peso dentro da Normalidade", "Cálculo de IMC", MessageBoxButtons.OK, MessageBoxIcon.Exclamation);
            else if (imc < 29.99)
                MessageBox.Show("SITUAÇÃO: Você está acima do peso", "Cálculo de IMC", MessageBoxButtons.OK, MessageBoxIcon.Exclamation);
            else if (imc < 34.99)
                MessageBox.Show("Atenção! Você está com Obesidade Grau I", "Cálculo de IMC", MessageBoxButtons.OK, MessageBoxIcon.Stop);
            else if (imc < 39.99)
                MessageBox.Show("Atenção! Você está com Obesidade Grau II(severa)", "Cálculo de IMC", MessageBoxButtons.OK, MessageBoxIcon.Stop);
            else
                MessageBox.Show("Atenção! Você está com Obsesidade Grau III(mórbida)", "Cálculo de IMC", MessageBoxButtons.OK, MessageBoxIcon.Warning);

        }
    }
}
