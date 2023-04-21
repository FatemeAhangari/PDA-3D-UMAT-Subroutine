# PDA-2D-UMAT-Subroutine
Progressive Damage Analysis (Modified Yamada-Sun / Hashin)

A progressive damage analysis based characteristic length method (PDA-based CLM) with only unidirectional layer properties required is proposed to predict the failure of notched composite. Two progressive damage models (PDMs), Hashin or modified Yamada–Sun criterion and Camanho’s degradation rules are recommended. The following is a UMAT subroutine for both Hashin and Modified Yamada-Sun failure criterion in Abaqus.
# Hashin criteria
In Abaqus, the Hashin failure criterion is available only to shell and continuum shell elements. Therefore this UMAT subroutine has been written, which can be used for continuum solid elements. The equations for the different failure modes are given below.
### Fiber Failure in Tension
When $\sigma_{11} > 0$
$$F_f = \Big(\frac{\sigma_{11}}{X_T}\Big)^2 + \frac{1}{S_{12}^2}( \tau_{12}^2 + \tau_{13}^2 )$$

### Fiber Failure in Compression
When $\sigma_{11} < 0$
$$F_f = \Big(\frac{-\sigma_{11}}{X_C}\Big)^2$$

### Matrix Failure in Tension
When $\sigma_{22} + \sigma_{33} > 0$
$$F_m = \frac{1}{Y_T^2}( \sigma_{22}^2 + \sigma_{33}^2) + \frac{1}{S_{23}^2}( \tau_{23}^2 - \sigma_{22}\sigma_{33}) + \frac{1}{S_{12}^2}( \tau_{12}^2 + \tau_{13}^2)$$

### Matrix Failure in Compression
When $\sigma_{22} + \sigma_{33} < 0$
$$F_m = \frac{1}{Y_C} \Bigl[  \Bigl(\frac{Y_C}{2S_{23}}\Bigr)^2  - 1 \Bigr] (\sigma_{22} + \sigma_{33}) + \frac{1}{4S_{23}^2}(\sigma_{22} + \sigma_{33})^2 + \frac{1}{S_{23}^2}( \tau_{23}^2 - \sigma_{22}\sigma_{33}) + \frac{1}{S_{12}^2}( \tau_{12}^2 + \tau_{13}^2)$$

# Modified Yamada-Sun
### Fiber Failure in Tension
When $\sigma_{11} > 0$
$$F_f = \Big(\frac{\sigma_{11}}{X_T}\Big)^2 + \Big(\frac{\sigma_{12}}{S_C}\Big)^2$$

### Fiber Failure in Compression
When $\sigma_{11} < 0$
$$F_f = \Big(\frac{\sigma_{11}}{X_C}\Big)^2 + \Big(\frac{\sigma_{12}}{S_C}\Big)^2$$

### Matrix Failure in Tension
When $\sigma_{22} + \sigma_{33} > 0$
$$F_m = \Big(\frac{\sigma_{22}}{Y_T}\Big)^2 + \Big(\frac{\sigma_{12}}{S_C}\Big)^2$$

### Matrix Failure in Compression
When $\sigma_{22} + \sigma_{33} < 0$
$$F_m = \Big(\frac{\sigma_{22}}{S_C}\Big)^2 + \Bigl[  \Bigl(\frac{Y_C}{2S_C}\Bigr)^2  - 1 \Bigr] \Big(\frac{\sigma_{22}}{Y_C}\Big) +  \Big(\frac{\sigma_{12}}{S_C}\Big)^2$$

### Fiber-Matrix shear
When $\sigma_{11} > 0$
$$F_f = \Big(\frac{\sigma_{11}}{X_T}\Big)^2 + \Big(\frac{\sigma_{12}}{S_C}\Big)^2$$
