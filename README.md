# FTIR-MD

see here:
SPINTRONICS/dynamics/TEST/water

Kim & Voth.  J. Chem. Phys., Vol. 116, No. 2, 8 January 2002 , see Eqs. (1) -(4)

FFI ot vel-vel autocorrelation function:

     w=frequency
     I(w)  = hhar * beta w^2 /(2 * pi) \Integral [dt* exp(-i w t)<u(0)* u(t)>
     I(w)  = hhar * beta / (2 * pi) \Integral [dt* exp(-i w t)< du(0)/dt * du(t)/dt>
     du/dt = \SUM_^atoms  [ dq_i/dt(t)*R(t) +q_i(t)* dR_i/dt ] 
