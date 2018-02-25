
n = 7;
SNR_db = -4:0.5:8;
SNR = 10.^(SNR_db./10); 
k = 4;
ber_7_4_hamming_hard = bercoding(SNR_db,'block','hard',n,k,4);
M = 4;
ber_4_4 = berawgn( SNR_db ,'psk',M,'nondiff');
ber_7_4_autoencoder = [ 0.37038  0.32722  0.29286  0.25436  0.21936  0.18242  0.1502  0.11876  0.09346  0.06972  0.04974  0.03586  0.02388  0.0169  0.00966  0.00574  0.00294  0.00154  0.00094  0.00034  0.00016  6e-05  3e-05  1e-05  8e-06 ];
%ber_7_4_fit = berfit(SNR_db,ber_7_4_autoencoder);
semilogy(SNR_db,ber_7_4_hamming_hard.*2,'b-.','linewidth',1),grid on,hold on;
semilogy(SNR_db,ber_7_4_autoencoder,'ro','linewidth',0.25,'MarkerFaceColor',[ 1 0 0]);

BER_SOFT=(7.*qfunc(sqrt(3*SNR)))+(7.*qfunc(sqrt(4*SNR)))+(qfunc(sqrt(7*SNR)));
semilogy(SNR_db,BER_SOFT./7,'b-','linewidth',1);
semilogy(SNR_db,ber_4_4.*4,'k','linewidth',1)
legend('Hamming (7,4) Hard Decision','Autoencoder(7,4)','Hamming (7,4) MLD','UnCoded BPSK(4,4)');
legend('Location','southwest');
ylim([1E-5 1]);
