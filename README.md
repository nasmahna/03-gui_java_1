## APLIKASI PENGHITUNG DEPRESIASI PER PERIODE AKTIVA SECARA LANGSUNG DENGAN METODE GARIS LURUS

```
public class FormDepresiasi extends javax.swing.JFrame {
    StringBuilder sb;
    int harga;
    int nilai;
    int umur;
    int hasilPerhitungan;

    public FormDepresiasi() {
        initComponents();
        
        sb = new StringBuilder();
    }
    
    
    public void loadHasilPerhitungan() throws HargaTidakBolehKosong, NilaiTidakBolehKosong, UmurTidakBolehKosong{
        
        try {
            harga = Integer.parseInt(txtHargaPerolehan.getText());
        } catch (NumberFormatException e) {
            throw new HargaTidakBolehKosong();
        } try {
            nilai = Integer.parseInt(txtNilaiResidu.getText());
        } catch (NumberFormatException e) {
            throw new UmurTidakBolehKosong();
        } try {
            umur = Integer.parseInt(txtUmurEkonomis.getText());
        } catch (NumberFormatException e) {
            throw new UmurTidakBolehKosong();
        }
        
        if (nilai == 0) {
            hasilPerhitungan = harga / umur;
        } else {
            hasilPerhitungan = (harga - nilai) / umur;
        }
        
        tempatHasil.setText(String.valueOf(hasilPerhitungan));
        }
        
    public void Reset() {
        txtHargaPerolehan.setText(null);
        txtNilaiResidu.setText(null);
        txtUmurEkonomis.setText(null);
        txtTahunAwal.setText(null);
        txtTahunAkhir.setText(null);
        taHasil.setText(null);
   }
   
   private void bttnHitungMouseClicked(java.awt.event.MouseEvent evt) {                                        
        // TODO add your handling code here:
        try 
        {
            this.loadHasilPerhitungan();
        } catch (HargaTidakBolehKosong e) 
        {
            JOptionPane.showMessageDialog(this, e.getMessage());
        } catch (UmurTidakBolehKosong e)
        {
            JOptionPane.showMessageDialog(this, e.getMessage());
        } catch (NilaiTidakBolehKosong e)
        {
            JOptionPane.showMessageDialog(this, e.getMessage());
        }
   }
   
  private void bttnResetMouseClicked(java.awt.event.MouseEvent evt) {                                       
        // TODO add your handling code here:
        this.Reset();
  }                 
  ```
    
        
