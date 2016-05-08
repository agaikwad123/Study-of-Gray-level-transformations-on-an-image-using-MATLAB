a= input (Enter the path of the image:); % accept image path from user

b= imread (a); % read the image

[x,y]=size (b); % store the image in matrix form

d=max (max (b)); % find he max value in the matrix
for i=1:x

for j=1:y

if(b(i,j))&lt;=50

f(i,j)= 0.2*(b(i,j));

elseif (50&lt;=(b(i,j))&lt;=150)

f(i,j)=2*(b(i,j)); %formula for contrast stretching;

elseif 150&lt;=b(i,j)&lt;=d

f(i,j)= 0.3*(b(i,j));

end

end

%Negative transform%

clc; clear all; close all;

% Negative transformation

a= input (&#39;Enter the path of the image: &#39;,&#39;s&#39;); % accept image path from user

b= imread (a); % read the image

[x,y]=size (b); % store the image in matrix form

d=max (max (b)); % find he max value in the matrix

for i=1:x

for j=1:y

fn(i,j)=d-b(i,j); %formula for negative transform of image

end

end

figure

subplot(1,2,1)

imshow(b) ; % show original image

title(&#39;Original image&#39;)

subplot(1,2,2)

imshow(fn) % show –ve transform of image

title(&#39;Negative image&#39;)

end

figure

subplot(1,2,1)

imshow(b) % show original image

title(Original image)

subplot(1,2,2)

imshow(f) % show transformed image

title(Contrast Stretching)
