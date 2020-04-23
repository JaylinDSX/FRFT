# FRFT
%%%
%%% FRACTIONAL FOURIER TRANSFORM (12.14.00)
%%% Hany Farid (farid@cs.dartmouth.edu | www.cs.dartmouth.edu/~farid)
%%%

clear;
set( gcf, 'Renderer', 'zbuffer' );

dim	= 64;
ramp	= 2*pi/dim * [-dim/2 : dim/2];
f	= exp(-ramp.^2);
f	= f - min(f);
f	= f';

%%% BUILD FOURIER BASIS
c = 1;
for k = -dim/2 : dim/2
	B(c,:) = 1/sqrt(dim+1) * exp( -j * k * ramp );
	c = c + 1;
end

