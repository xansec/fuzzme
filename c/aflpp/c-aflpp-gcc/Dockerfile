FROM fuzzers/aflplusplus:3.12c
COPY src/fuzzme.c .
RUN afl-gcc-fast fuzzme.c -o /fuzzme 
RUN echo seed > /corpus/seed

# Set to fuzz!
ENTRYPOINT ["afl-fuzz", "-i", "/corpus", "-o", "/out"]
CMD ["/fuzzme", "@@"]
